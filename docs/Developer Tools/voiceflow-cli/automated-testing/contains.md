---
title: Interaction-Based Examples
deprecated: false
hidden: false
metadata:
  robots: index
---
# Example using `contains` validation

## Suite file

```yaml
# suite.yaml

name: Example Suite
description: Suite used as an example
environmentName: production
# Optional: Create a new user session for each test (default: false)
# When enabled, each test will run with a fresh user session
newSessionPerTest: true
tests:
  - id: test_id
    file: ./test.yaml
```

## Test file

```yaml
# test.yaml

name: Example test
description: These are some tests
interactions:
  - id: test_1
    user: 
      type: text
      text: hi
    agent:
      validate:
        - type: contains
          value: hello
```

<br />

```yaml
# test.yaml

name: Example test
description: These are some tests
interactions:
  - id: test_1
    user: 
      type: text
      text: hi
    agent:
      validate:
        - type: contains
          value: hello
```
