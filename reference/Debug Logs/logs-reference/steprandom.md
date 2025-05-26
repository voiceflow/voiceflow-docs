---
title: step.random
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Examples
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"level\": \"info\",\n  \"timestamp\": \"2022-06-15T14:15:30.150Z\",\n  \"kind\": \"step.random\",\n  \"message\": {\n    \"componentName\": \"random\",\n    \"stepID\": \"628469f0effe73d544505715\",\n    \"path\": {\n      \"componentName\": \"speak\",\n      \"stepID\": \"62c47ac699eca10006f20cbb\"\n    }\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]
`path` is `null` when the chosen path does not connect to a node on the canvas.