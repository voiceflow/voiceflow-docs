---
title: PII redaction (beta)
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
The PII Redaction feature, now available in beta, automatically detects and redacts sensitive personal information from your conversation transcripts and logs. This guide will walk you through enabling and using this feature.

## Enabling PII Redaction:

1. Navigate to your agent's settings and go to the "Behavior" tab.
2. Under "Personalization," you will find the "PII Redaction" toggle.
3. Toggle on "PII Redaction" to enable the feature for your agent.

Please note that PII Redaction is disabled by default for all existing and new agents. You must manually enable it in the settings.

## Testing PII Redaction:

- To test PII Redaction, you must interact with your agent in a `production` environment.
- PII Redaction will not work during development testing (in-app omnipresent testing or the canvas console) to allow for easier debugging.
- To test, use the Voiceflow Web Widget snippet with the version ID set to "production" and publish your agent.

## Viewing Redacted Transcripts:

1. Navigate to the "Transcripts" tab in Voiceflow.
2. The transcript logs will display the conversation with sensitive information redacted by the LLM.
3. Redaction applies to both user and AI agent messages, as well as debug logs.

### Fetching Unredacted Transcripts via API:

- During the beta, you can fetch unredacted transcripts via the Transcripts API within a two-day time-to-live (TTL) period.
- To retrieve unredacted transcripts, you must pass `encrypted=true` as a query parameter in your API request.
- Example API request:
  ```
  curl --request GET \
       --url https://api.voiceflow.com/v2/transcripts/xyz/xyz?encrypted=true \
       --header 'accept: application/json'
  ```

## Important Notes:

- During the beta, you cannot unredact the redacted information directly from the Transcripts UI.
- After the two-day TTL expires, unredacted transcripts will no longer be accessible by anyone, including Voiceflow.

## Credit Consumption:

- During the beta period, using PII Redaction will consume credits/tokens from your account's quota.
- For testing purposes, you can disregard the token accumulation during the beta and focus on thoroughly testing the feature.

## Feedback and Support:

We highly value your feedback during this beta period. Please test the PII Redaction feature extensively and provide us with your thoughts, suggestions, and any issues you encounter. Your input will help us refine the feature and prioritize future developments as we work towards general availability (GA).

If you have any questions or need assistance, please don't hesitate to reach out to our support team.