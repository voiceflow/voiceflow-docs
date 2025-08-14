---
title: Creating new projects
excerpt: Start a project from scratch or generate one using a prompt
deprecated: false
hidden: true
metadata:
  robots: index
---
Voiceflow allows you to start a project from scratch or to generate an initial version of a project using a prompt.

## Creating a project manually

Creating a project manually lets you start from scratch or from a pre-built template. This lets you start from an (almost) blank canvas and build our your agent.

To create a project manually, choose one of the templates shown on the homepage of Voiceflow's dashboard.

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NSHpk6cJYEDcI1dJrGuslpUkKHt82TXNPVBFvC" />

<br />

Once your agent project is set up, take it further with these improvements to expand its capabilities and performance:

* [ ] **Create your own custom agent**\
  Create your own agent from scratch with a new prompt or use a pre-created template.
  See: <Anchor label="Agent step reference" target="_blank" href="https://docs.voiceflow.com/docs/agents#/">Agent step reference</Anchor>

* [ ] **Enable necessary integrations**\
  Activate 3rd-party integrations your Agent will need to complete tasks across your workspace(e.g. Google Sheets, Hubspot, Airtable, etc).
  See: <Anchor label="Integrations reference" target="_blank" href="https://docs.voiceflow.com/docs/integrations#/">Integrations reference</Anchor>

* [ ] **Choose your interfaces**\
  Use your Voiceflow agent from phone, web and chat interfaces.
  See: <Anchor label="Interfaces guide" target="_blank" href="https://docs.voiceflow.com/docs/projects#/">Interfaces guide</Anchor>

<br />

## Generate a project

Alternatively, you can also use project generation to spin up a quick project. Project generation allows you to create a starting-point agent by providing a prompt that describes the agent's intended workflow. This method is designed to help you go from idea to working draft quickly.

To generate a project, head to Voiceflow's dashboard and enter a prompt into the project generation input. If you're not sure what to put, we recommend starting with one of the provided templates. Once you've entered your prompt, click the blue button and your project will be generated in around 30 seconds.

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NS7DoJLnKUJ2mGoWcAYZ4TIKVbRjQtdHvh1CLu" />

<Callout icon="ℹ️" theme="info">
  **FYI:** Project generation is best used as a *starting point* for your project. Always review and refine the generated workflow to ensure accuracy and completeness. Currently, this is also a **BETA** feature, subject to changes.
</Callout>

<br />

Before you start using a generated project, we advise you double check your workflow:

* [ ] **Review workflow structure**\
  Ensure the generated steps match your intended flow of conversation and actions.

* [ ] **Refine step prompts**\
  Review and update each step’s prompt text to be more specific and tailored to your use case, if necessary.

* [ ] **Confirm tool usage**\
  Check that all required tools are enabled and correctly configured.

* [ ] **Validate logic and conditions**\
  Verify branching, triggers, and conditions behave as expected.

* [ ] **Be specific in future prompts**\
  When regenerating or iterating, clearly describe the desired flow and Agent behavior.

<br />

### Best practices for project generation

When using project generation, here are some things to keep in mind when you write your prompt:

* Include **clear goals and intentions** for what the generated project should achieve.
* Describe **key user interactions** and decision points.
* List **integrations or APIs** the project should use.
* Specify **any unique constraints** (e.g., compliance requirements, tone of voice).
* Avoid vague terms - precise language improves the generated workflow.