---
title: Quick Start
deprecated: false
hidden: false
metadata:
  robots: index
---
`voiceflow-cli` is a command-line tool that allows Voiceflow users to upload files to their knowledge base, download transcripts, and run automated tests.

This guide will walk you through installing the CLI, authenticating your agent, and uploading a document to your knowledge base.

<br />

## 1. **Install the CLI**

Open your terminal, then input the following command. This command installs the Voiceflow CLI:

```curl
curl -sfL https://voiceflow.xavidop.me/static/run | bash
```

Alternatively, you can install it via Chocolatey (Windows) or APT (Linux). Click here to learn more.

RECORD VIDEO FOR WHAT WE SHOLD SEE AFTER ENTERING COMMAND!!1

<br />

If you don't see the same screen as in the same terminal that you ran the initial command:

mikaal write this

```bash
bash
CopyEdit
voiceflow --help
```

You should see a list of commands like in the image below, that means it worked. You’re set!

<br />

## 2. **Grab your agent's API key**

* Open the [Voiceflow Creator](https://creator.voiceflow.com/), and click the agent you want to use
* Click Interfaces in the sidebar and open the API Keys tab
* Click the **copy** button to grab your API key

<br />

## 3. **Add the agent's API key to the environment**

Run the following command, making sure you replace `YOUR_KEY` with the copied API key from the previous step.

```Text bash
export VF_API_KEY=YOUR_KEY
```

<br />

## 4. **Upload a URL to your agent's Knowledge Base**:

```bash
voiceflow document upload-url --url https://docs.voiceflow.com/docs/cli-quick-start.md --name "Quick Start"
```

You’ll see a pending message while it processes.

<br />

### 5. Check your Knowledge Base at creator

* Go back to your Voiceflow browser, and head over to the 'Knowledge base' button in your sidebar
* You should see your newly updated file as shown below