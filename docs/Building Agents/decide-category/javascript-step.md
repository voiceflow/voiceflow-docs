---
title: JavaScript step
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
The JavaScript step allows you to write and execute JavaScript (ES6 on V8) code within your assistant directly.

Some use cases of a JavaScript step include JSON data manipulation, variable and entity data processing, and last_utterance variable handling.

> 📘 Consider if a [function](https://developer.voiceflow.com/v2.0/docs/custom-functions) is more appropriate for your use case
> 
> The JavaScript step should only be used for one-off and short code snippets, with simple variable parsing, updates or JSON formatting. For anything longer than a couple of lines of code, and that should be re-usable in your project, making a [function](https://developer.voiceflow.com/v2.0/docs/custom-functions) will be easier and better.

## Using variables in your code

The code step automatically exposes all of your variables to be used within the code step directly. To use variables within the code step, simply type the name of the variable, there is no need to add curly braces ({ }). If variables are updated to be equal to undefined, they’ll be saved as `null` because variables do not support being _undefined_.

For example, if there is an assistant variable called score, to update the score by 1 you would just write: `score = score + 1;`.

![](https://files.readme.io/2178e8d-image.png)

## Standard paths

The code step has two standard paths: `Default` and `Fail`. The Default path will be followed if your code is successfully run, and the Fail path will be followed if your code fails to run or has an error during its execution.

## Custom paths

It is possible to conditionally branch the flow based on code. You can add **up to 10 custom paths** in a code step, and give a custom name for each path.

To go down a path, simply call return `"path_name"` within the code. If nothing is returned, it will use the Default path.

Example: there are two custom paths: `"victory"`, `"defeat"`, the code would look like:

```javascript
if (score > 100) { 
  return "victory" 
} else if (score < 0) { 
  return "defeat" 
} 
// otherwise it will go down the Default path here
```

![](https://files.readme.io/5c82248-image.png)

## Are there any Code Step constraints to consider?

Some constraints to consider when using the Code Step include:

- Code Steps **cannot be used to make requests to external servers**, so cannot be used to call external APIs. Alternatively, you can use the API Step to pull or push data between your Voiceflow agent and a third-party system, or [functions](https://developer.voiceflow.com/v2.0/docs/custom-functions).
- Code Steps do not currently support importing modules.
- Code Steps cannot be used to create new variables. Any variables that you want to use after the Code Step is executed must already exist before being referenced in the Code Step.

## Why do I get a TypeError debug message when I test a Code Step using the prototype tool?

Currently, if an existing Voiceflow variable is not set by the time the Code Step begins executing, the value of that variable is `0`. For example, if the Code Step attempts to execute a String method on a variable that is not yet set, a TypeError will occur.