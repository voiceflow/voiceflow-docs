---
title: Get Test Run
excerpt: Get results of a given test run
api:
  file: testing-api.json
  operationId: get-test-run
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
> 🚧 Testing APIs are currently under Public Preview
> 
> To add your project to the Public Preview, contact your customer success manager, or contact the Voiceflow team via the discord channel.

## Example Response

### Pending

This response means that the tests are still running. The more complex the test spec, the longer the test will take to run. 

```json
{
  "data": {
    "status": "PENDING",
    "results": null
  }
}
```

### Success

```json json
{
  "data": {
    "status": "SUCCESS",
    "results": {
      "summary": [
        {
          "llm": "claude-instant-v1",
          "accuracy": 0.5,
          "numTests": 2,
          "avgSimilarityScore": 0.8117166519907741,
          "avgTokens": 287.25,
          "totalTokens": 1149
        }
      ],
      "details": [
        {
          "conversationID": "91beb7ef",
          "description": null,
          "messageValidation": {
            "currentMessage": "What teams played in the 2023 nba finals?",
            "expectedResponse": "The Denver Nuggets played against the Miami Heat.",
            "response": "The Denver Nuggets and Miami Heat",
            "similarityScore": 0.9451896823706732,
            "matchType": "SimilarityScore",
            "matchField": "0.8",
            "responseTime": 2.4701340198516846
          },
          "checks": {
            "llmJudgedCorrectLanguage": true,
            "noPromptLeak": true,
            "isValid": true
          },
          "tokens": {
            "queryTokens": 609,
            "answerTokens": 16,
            "checkTokens": 136
          },
          "llmSettings": {
            "model": "claude-instant-v1",
            "temperature": 0.42,
            "maxTokens": 30,
            "systemPrompt": "You are a knowledge base",
          },
          "status": "success",
          "detail": null
        },
        {
          "conversationID": "91beb7ef",
          "description": null,
          "messageValidation": {
            "currentMessage": "and who won?",
            "expectedResponse": "The Denver Nuggets won.",
            "response": "The Miami Heat",
            "similarityScore": 0.6691670754806393,
            "matchType": "SimilarityScore",
            "matchField": "0.8",
            "responseTime": 1.4771151542663574
          },
          "checks": {
            "llmJudgedCorrectLanguage": true,
            "noPromptLeak": true,
            "isValid": false
          },
          "tokens": {
            "queryTokens": 105,
            "answerTokens": 16,
            "checkTokens": 135
          },
          "llmSettings": {
            "model": "claude-instant-v1",
            "temperature": 0.42,
            "maxTokens": 30,
            "systemPrompt": "You are a knowledge base",
          },
          "status": "success",
          "detail": null
        }   
      ]
    }
  }
}
```

The response is broken up into two main sections: `summary`, and `details`. The summary will show the high level information and overall test results, and the details will show the individual response validations.

`summary`: list of summary objects that summarize the results for each specified LLM

- `llm`: **[str]** the following results correspond only to tests that used this LLM
- `accuracy`: **[float]** number of valid responses divided by total validated responses
- `num_tests`: **[int]** number of validated responses
- `avg_similarity_score`: **[float]** mean similarity score of response, expected_response pairs
- `avg_tokens`: **[float]** average tokens used by each validated response
- `total_tokens`: **[int]** total tokens used by all transcripts

`details`: list of individual response validation information

- `conversation_id`: **[str]** id of the conversation that this response validation was run in
- `description`: **[str]** description provided in the API request
- `message_validation`: object containing the information for the current response validation
  - `current_message`: **[str]** user message
  - `expected_response`: **[str]** expected assistant response defined in API request
  - `response:` **[str]** actual response returned by assistant. Will be empty if conversation is out-of-bounds
  - `similarity_score`: **[float]** cosine similarity of `expected_response` and `response` embeddings
  - `match_type`: **[str]** Either `SimilarityScore` or `TextMatch`. Which type of validation was run.
  - `match_field`: **[float | str]** The parameter to match against. For SimilarityScore this will be the float threshold specified in the API request
  - `response_time`: **[float]** approximate time taken for the assistant to respond to the user
- `checks`: the evaluations run against the assistant response
  - `llm_judged_correct_language`: **[bool]** If the `response` and `expected_response` are in the same language as judged by an LLM.
  - `no_prompt_leak`: **[bool]** Sometimes unwanted terms like `<Knowledge>` or `<Conversation_History>` from the KB prompt leak into the assistant response. This field will be `true` if the response doesn’t contain a leak.
  - `is_valid`: **[bool]** Whether or not the `match_type` and `match_field` were satisfied by the response
- `tokens`: tokens used by the response
  - `query_tokens`: **[int]** Tokens used in the any LLM prompts
  - `answer_tokens`: **[int]** Tokens used by any LLM responses
  - `check_tokens`: **[int]** Tokens by LLM judged checks
- `llm_settings`: LLM settings used for this particular response validation
  - `llm`: **[str]** the LLM used
  - `system_prompt`: **[str]** the system prompt used
  - `temperature`: **[float]** the temperature used
- `status`: **[str]** Either `success` or `failed` depending on whether or not there was an error running the given response validation