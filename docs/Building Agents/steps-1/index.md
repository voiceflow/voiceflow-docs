---
title: Steps
deprecated: false
hidden: false
metadata:
  robots: index
---
Agents on Voiceflow can be built in three ways: using an agentic approach, a deterministic approach, or a combination of both.

## Agentic approach

Building an agent in an agentic way means giving the agent the autonomy to reason, automatically make decisions, and respond dynamically based on context, rather than following a fixed flow. This can be done using Voiceflow's [Agent step](doc:agents).

<Cards columns={1}>
  <Card title="Agent step" href="https://docs.voiceflow.com/docs/agents" icon="fa-robot">
    Combine a prompt, tools, and paths to intelligent conversational agents.
  </Card>
</Cards>

## Deterministic approach

Building an agent in a deterministic way means designing a fixed, rule-based flow where every user interaction follows a predefined path. This approach gives you full control over the conversation logic and is useful when consistency, structure, or compliance is required.

We have four types of steps that allow you to build deterministic agents.

<Cards columns={4}>
  <Card title="Talk steps" href="https://readme.com" icon="fa-messages" target="_blank">
    Send text, image, and interactive messages to the user.
  </Card>

  <Card title="Listen steps" icon="fa-ear">
    Collect useful information from the user.
  </Card>

  <Card title="Logic steps" icon="fa-gears">
    Dynamically route the conversation based on user input.
  </Card>

  <Card title="Dev steps" icon="fa-code">
    Add custom code, API calls, and more to your agent.
  </Card>
</Cards>