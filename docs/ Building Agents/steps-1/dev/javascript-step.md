---
title: JavaScript step
excerpt: Run custom JavaScript to manipulate variables or control logic.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<Image align="center" src="https://files.readme.io/066734229cab35b1378481902918e55d24605558c46b433d08a7f2cb018a587c-Image_7.png" />

The JavaScript step lets you write and execute short JavaScript snippets (ES6 on V8) directly in your agent. It’s useful for logic that doesn’t require an external API call or reusable function like parsing JSON, modifying variables, or adding conditional paths.

This step runs once when reached and evaluates immediately. If your use case involves longer or reusable code, we recommend using a [Function](doc:functions) instead.

## Basic usage

To use the JavaScript step, drag it onto the canvas and click into the step to open the code editor.

All of the agent's variables are automatically available for use—no need to reference them with curly braces. You can update variable values by reassigning them directly.

Example:

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

* Code Steps **cannot be used to make requests to external servers**, so cannot be used to call external APIs. Alternatively, you can use the API Step to pull or push data between your Voiceflow agent and a third-party system, or [functions](https://developer.voiceflow.com/v2.0/docs/custom-functions).
* Code Steps do not currently support importing modules.
* Code Steps cannot be used to create new variables. Any variables that you want to use after the Code Step is executed must already exist before being referenced in the Code Step.

## Why do I get a TypeError debug message when I test a Code Step using the prototype tool?

Currently, if an existing Voiceflow variable is not set by the time the Code Step begins executing, the value of that variable is `0`. For example, if the Code Step attempts to execute a String method on a variable that is not yet set, a TypeError will occur.