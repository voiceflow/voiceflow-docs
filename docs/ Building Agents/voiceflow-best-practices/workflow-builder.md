---
title: Workflow Builder
excerpt: Best practices for Voiceflow's Workflow Builder.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Workflow Builder Best Practices

Workflows are where the actual conversation logic resides. Each workflow should focus on a single main flow or functionality, addressing specific user needs or goals. However, it's important to note that a single workflow can have multiple entry points or triggers.

**Key Workflow Characteristics:**

1. **Single Main Flow:** Each workflow should encapsulate one primary conversation flow or functionality.
2. **Multiple Triggers:** A workflow can be initiated by various triggers, such as:

* Multiple intents (different ways a user might ask for the same information)
* External triggers (e.g., API calls, scheduled events)
* Button clicks or other UI interactions

This design allows for flexibility in how users can access a particular functionality while maintaining a clear, focused purpose for each workflow.

**Example:** Let's consider a "Check Account Balance" workflow within the "Balance Inquiries" subfolder of our Banking Agent:

**Main Flow:** Retrieve and present the user's account balance

**Triggers:**

Intent: "What's my account balance?"\
External: Scheduled daily balance notification\
UI: "Check Balance" button click in the banking app

While all these triggers lead to the same primary function (checking the account balance), having multiple entry points makes the Agent more flexible and user-friendly, accommodating various ways users might try to access this information.

The workflow itself would contain the steps to:

1. Authenticate the user (possibly using an Authentication component)
2. Determine which account to check (using an Account Selector component if the user has multiple accounts)
3. Retrieve the balance information
4. Format and present the balance to the user
5. Offer related actions (e.g., "Would you like to see recent transactions?" or "Do you want to set a balance alert?")

> 💡 Pro tip
>
> When designing workflows, consider how users might try to access the functionality. Including multiple intents and triggers make your Agent more robust and user-friendly. However, to avoid confusion, do not overlap intents between different workflows.

<br />

## Canvas organization

The canvas of the Workflow Builder is where you visually design and implement your Agent's conversation flows. As Agents get more complex, so do the canvases within the Workflow Builder. Voiceflow has many tools to keep your canvas organized, readable, and scalable.

### Components: Reusable Building Blocks

Components in Voiceflow are reusable modules that handle specific functions or tasks. They promote consistency and efficiency by allowing you to use the same functionality across different workflows.

**Example:**\
For our Banking Agent, some essential components might include:

* **Account Authenticator:**
  * Function: Verifies the user's identity before allowing access to sensitive information or actions.
  * Usage: This component could be used in balance inquiries, transfers, or account settings changes workflows.
* **Account Selector:**
  * Function: Allows users to specify which account they're referring to (e.g., checking, savings, credit card).
  * Usage: This could be used in balance inquiries, transaction history requests, or transfer workflows.
* **Error Handling:**
  * Function: Manages fallbacks when the Agent doesn't understand user input and handles various error scenarios.
  * Usage: This component can be integrated into any workflow to provide consistent error management across the entire Agent.
* **Transfer To Agent:**
  * Function: Determines when to offer a handover to a human Agent and manages the transfer process.
  * Usage: This can be triggered from the Error Handling Flow or directly from workflows dealing with complex or sensitive issues.

By creating these components, you ensure consistency in handling these common tasks across your Agent, and you can easily update them in one place if needed.

### Actions: Quick Operations and Navigation

Actions in Voiceflow allow you to perform simple operations or navigate within your Agent without needing a full step or block.

#### Key points about Actions:

* They can be added from pre-existing steps
* Actions appear as chips linked to a step's path exit on the canvas
* Some actions have exits that allow you to move on after the action is executed

**Types of actions include:**

1. **Navigation Actions:**

* Go to Block: Jumps to a specific block in your Agent
* Go to Intent: Moves to a specific intent
* End: Terminates the current conversation flow

2. **Backend Actions:**

* Set Variable: Allows you to set or modify variable values
* Open URL: Opens a specified URL (typically used in button steps)
* API: Executes an API call
* Custom Code: Runs a small piece of custom code

#### How add an Action:

1. Drag out a new arrow from the end of a step
2. Select the desired action from the dropdown menu

Actions are particularly useful for creating more streamlined and efficient workflows by allowing you to perform quick operations without cluttering your canvas with additional blocks.

### Canvas Organization Techniques

* Color Coding Blocks and Connection Lines
* Color coding blocks and connection lines enables conversation design artifacts to be easily readable at a glance. This technique provides benefits for both designers and developers:
  1. For designers:
     * Use color to keep track of related groups of elements
     * Color code different types of transitions between blocks
  2. For developers:
     * Colors provide an instant birds-eye view of the overall flow
     * Colors help visualize relationships within an experience

#### Precise Labeling

Precise labels are crucial for:

* Enabling searching across an assistant
* Making it easy to design jumps across blocks, flows, intents, and domains
* Allowing other designers to understand logic without needing to comprehend complex if-then situations

#### Layout Best Practices

When laying out your blocks and arrows:

* Aim for a logical, left-to-right or top-to-bottom flow
* Minimize crossing arrows to reduce visual complexity
* Group related blocks together
* Use consistent spacing between blocks
* Consider using swimlanes to separate different types of functionality or user paths
