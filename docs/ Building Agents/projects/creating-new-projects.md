---
title: Creating new projects
excerpt: >-
  Learn how to start a new Voiceflow Agent project; either from scratch or by
  using prompt-based Project Generation.
deprecated: false
hidden: true
metadata:
  robots: index
---
Get started with Voiceflow instantly through project generation, or create a project from scratch with templates or the Voiceflow Creator. This guide covers both methods, what to expect from each, and the steps to ensure your Agent is ready for deployment.

# 1. Creating a project manually

Manual creation gives you full control from the start with Voiceflow Creator, allowing you to design your Agent’s workflow exactly as you intend.

## Basic usage

\[video]

***

## Checklist for manual project setup

After connecting the **Agent** step to the start chip:

* **Create your own custom agent**\
  Create your own agent from scratch with a new prompt or use a pre-created template.
  See: [Agent Step Reference](#)

* **Enable necessary integrations**\
  Activate 3rd-party integrations your Agent will need to complete tasks across your workspace(e.g. Google Sheets, Hubspot, Airtable, etc).
  See: [Integrations Reference](#)

* **Choose your deployment channels**\
  Use your Voiceflow Agent from Phone or Chat interfaces.
  See: [Deployments Guide](#)

* **Extend functionality through automation**\
  Connect with 7,000+ apps via Zapier to trigger external actions or sync data.
  See: [Zapier Integration](#)

***

# 2. Using project generation

Project Generation allows you to create a starting-point agent by simply providing a natural language prompt that describes the agent's intended workflow.

## Basic Usage

\[ video ]

***

## About project generation

This method is designed to help you go from idea to working draft quickly. You provide a descriptive prompt, and Voiceflow will generate an initial agent workflow with steps, prompts, and tool selections.

<Callout icon="📘" theme="info">
  **Important:** Project generation is best used as a *starting point* for your project. Always review and refine the generated workflow to ensure accuracy and completeness. Currently, this is also a **BETA** feature, subject to changes.
</Callout>

> **Important:** Workflow Generation is best used as a foundation. Always review and refine the generated workflow to ensure accuracy and completeness.

***

### Post-generation review

Before you start using a generated project, we advise you double check your workflow:

* **Review workflow structure**\
  Ensure the generated steps match your intended flow of conversation and actions.

* **Refine step prompts**\
  Review and update each step’s prompt text to be more specific and tailored to your use case, if nessecary.

* **Confirm tool usage**\
  Check that all required tools are enabled and correctly configured.

* **Validate logic and conditions**\
  Verify branching, triggers, and conditions behave as expected.

* **Be specific in future prompts**\
  When regenerating or iterating, clearly describe the desired flow and Agent behavior.

***

### Best practices for project generation

* Include **clear goals and intentions** for what the generated project should achieve.
* Describe **key user interactions** and decision points.
* List **integrations or APIs** the project should use.
* Specify **any unique constraints** (e.g., compliance requirements, tone of voice).
* Avoid vague terms- precise language improves the generated workflow.

***

## Summary

Whether you build manually or with project generation, the end goal is the same: an agent ready for real-world deployment. Manual creation offers granular control from the start. Project generation accelerates the initial setup but requires thorough review and customization.

See also:

* [Agent Step Reference](#)
* [Integrations Reference](#)
* [Deployments Guide](#)
* [Zapier Integration](#)