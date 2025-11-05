---
title: 'Express.js sample: working with organization event webhooks'
description: >-
  Learn how to receive organization-level events from Voiceflow, validate the
  request came from Voiceflow, then do an action based on the data and type of
  event received.
hidden: false
recipe:
  color: '#018FF4'
  icon: 🪝
---
```javascript JavaScript
// This is a sample Express.js app that verifies that a organization-level webhook
// event comes from Voiceflow, then logs and returns a message whenever a new
// project is created.

import express from 'express';
import crypto from 'crypto';

const app = express();
const SECRET = process.env.VOICEFLOW_WEBHOOK_SECRET; // e.g. "whsec_abc123..."

if (!SECRET?.startsWith('whsec_')) {
  console.error('Set VOICEFLOW_WEBHOOK_SECRET to your Svix signing secret (whsec_...)');
  process.exit(1);
}

app.post('/webhooks/voiceflow', express.raw({ type: 'application/json' }), (req, res) => {
  try {
    // --- 1) Read Svix headers ---
    const id = req.get('svix-id');
    const ts = req.get('svix-timestamp'); // seconds
    const sigHeader = req.get('svix-signature'); // e.g. "v1,BASE64"
    if (!id || !ts || !sigHeader) return res.status(400).send('Missing headers');

    // --- 2) Build signed content & compute expected signature ---
    const signed = `${id}.${ts}.${req.body.toString('utf8')}`;
    const key = Buffer.from(SECRET.split('_')[1], 'base64');
    const expected = crypto.createHmac('sha256', key).update(signed).digest('base64');

    // Header can include multiple versions; accept any that matches
    const provided = sigHeader
      .split(' ')
      .map(p => p.split(',')[1])
      .filter(Boolean);

    const isValid = provided.some(p => {
      const a = Buffer.from(p || '');
      const b = Buffer.from(expected);
      return a.length === b.length && crypto.timingSafeEqual(a, b);
    });

    if (!isValid) return res.status(400).send('Bad signature');

    // --- 3) Safe to parse and handle the event ---
    const event = JSON.parse(req.body.toString('utf8'));

    if (event?.type === 'organization.project.created') {
      const email = event?.data?.createdBy?.userEmail;
      const projectID = event?.data?.projectID;

      if (email && projectID) {
        console.log(`${email} created a new project with the ID ${projectID}`);
        return res.json({ message: `${email} created a new project with the ID ${projectID}` });
      }
    }

    return res.status(204).end();
  } catch (e) {
    console.error('Webhook error:', e.message);
    return res.status(400).send('Invalid request');
  }
});

// Minimal health check
app.get('/', (_req, res) => res.send('OK'));

app.listen(process.env.PORT || 3000, () =>
  console.log('Listening on http://localhost:3000')
);
```

# Get everything setup

<!-- javascript@5-14 -->

Import the required dependencies, create an Express app, and validate that the VOICEFLOW_WEBHOOK_SECRET environment variable is set.

# Validate that the event was sent by Voiceflow

<!-- javascript@16-41 -->

When a new event is received by the webhook, validate that the event was actually sent by Voiceflow by verifying its signature. If it wasn't sent by Voiceflow, return an error.

# Handle the event

<!-- javascript@43-56 -->

If the event type is "organization.project.created", log and return a message containing the creator's email and the project ID.

If the event is another other type, just return a 204 status code.