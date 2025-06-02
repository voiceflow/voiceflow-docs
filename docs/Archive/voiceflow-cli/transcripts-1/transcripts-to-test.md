---
title: Transcripts to test
deprecated: false
hidden: false
metadata:
  robots: index
---
# Transform transcripts into tests

## Overview

Convert a Voiceflow transcript into a reusable [test case](/tests/tests).

## Command

```bash
voiceflow transcript to-test [flags]
```

## Parameters

### Required flags

* `--agent-id`: Voiceflow Agent ID
* `--transcript-id`: ID of the transcript to convert

### Optional flags

* `--output-file`: Path to save the generated test (default: test.yaml)
* `--test-name`: Name for the generated test
* `--test-description`: Description for the generated test

## Examples

### Basic usage

```bash
voiceflow transcript to-test \
  --agent-id your-agent-id \
  --transcript-id transcript-123
```

### Full example with options

```bash
voiceflow transcript to-test \
  --agent-id your-agent-id \
  --transcript-id transcript-123 \
  --output-file my-test.yaml \
  --test-name "Payment Flow Test" \
  --test-description "Validates the payment processing dialogue"
```

## Output

The command generates a YAML file containing:

* Test metadata (name, description)
* User interactions
* Expected agent responses
* Validation rules