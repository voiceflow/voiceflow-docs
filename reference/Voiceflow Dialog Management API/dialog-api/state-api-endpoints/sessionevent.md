---
title: Session Event
excerpt: Sends an event to an ongoing session.
api:
  file: voiceflow-dialog-management-api.json
  operationId: sessionEvent
hidden: false
---
> 🚧 voice only
>
> Session events can only be broadcasted to voice conversations, we're looking to extend this functionality to chat in the future.

This endpoint is intended to allow external events to update the state of the conversation.

An example is filling out a form, this may take a long time. When it is submitted, this endpoint can be invoked to have the agent acknowledge the submission.

All voice conversations will have an assigned `{session_id}` variable, unique to every call.

If the agent is busy or in the middle of something, the event action will be "queued" and invoked when the agent is done. There can only be one action queued at a time, it is recommended to not call this endpoint frequently.