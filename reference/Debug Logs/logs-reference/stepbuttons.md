---
title: step.buttons
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
### Follow path
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"level\": \"info\",\n  \"timestamp\": \"2022-06-15T14:15:30.150Z\",\n  \"kind\": \"step.buttons\",\n  \"message\": {\n    \"componentName\": \"buttons\",\n    \"stepID\": \"628469f0effe73d544505715\",\n    \"intent\": null,\n    \"url\": null,\n    \"path\": {\n      \"componentName\": \"speak\",\n      \"stepID\": \"62c47ac699eca10006f20cbb\"\n    }\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]
### URL + follow path
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"level\": \"info\",\n  \"timestamp\": \"2022-06-15T14:15:30.150Z\",\n  \"kind\": \"step.buttons\",\n  \"message\": {\n    \"componentName\": \"buttons\",\n    \"stepID\": \"628469f0effe73d544505715\",\n    \"intent\": null,\n    \"url\": \"https://example.com\",\n    \"path\": {\n      \"componentName\": \"speak\",\n      \"stepID\": \"62c47ac699eca10006f20cbb\"\n    }\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]
### Go to intent
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"level\": \"info\",\n  \"timestamp\": \"2022-06-15T14:15:30.150Z\",\n  \"kind\": \"step.buttons\",\n  \"message\": {\n    \"componentName\": \"buttons\",\n    \"stepID\": \"628469f0effe73d544505715\",\n    \"intent\": \"place_order\",\n    \"url\": null,\n    \"path\": null\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]
### URL + go to intent
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"level\": \"info\",\n  \"timestamp\": \"2022-06-15T14:15:30.150Z\",\n  \"kind\": \"step.buttons\",\n  \"message\": {\n    \"componentName\": \"buttons\",\n    \"stepID\": \"628469f0effe73d544505715\",\n    \"intent\": \"place_order\",\n    \"url\": \"https://example.com\",\n    \"path\": null\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]