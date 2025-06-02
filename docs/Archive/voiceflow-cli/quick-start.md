---
title: Quick Start
deprecated: false
hidden: false
metadata:
  robots: index
---
`voiceflow-cli` is a command-line tool that allows Voiceflow users to upload files to their knowledge base, download transcripts, and run automated tests.

This guide will teach you how to setup your Voiceflow CLI, authenticate your agent, and upload a document to your knowledge base.

<br />

## 1. **Install the CLI**

Open your terminal, then input the following command. This command installs the Voiceflow CLI:

```curl
curl -sfL https://voiceflow.xavidop.me/static/run | bash
```

Alternatively, you can install this using homebrew, chocolatey, or apt. Click here to learn more.

RECORD VIDEO FOR WHAT WE SHOLD SEE AFTER ENTERING COMMAND!!1

<br />

If you don't see xyz in the same terminal that you ran the initial command:

```bash
bash
CopyEdit
voiceflow --help
```

You should see a list of commands like in the image below, that means it worked. You’re set!

<br />

## 2. **Grab your agent's API key**

* Open the [Voiceflow Creator](https://creator.voiceflow.com/), and click on the agent you want to use with the Voiceflow CLI
* Click on the 'interfaces' button on the side bar, and then click on 'API keys'
* Once you the agent key, click the 'copy' button

<br />

## 4. **Upload your file**

Put your file (`test.txt`, `faq.pdf`, etc.) in the folder you’re working from in your IDE. Then run:

```bash
bash
CopyEdit
voiceflow document upload-file \
  --file ./yourfile.pdf \
  --voiceflow-api-key YOUR_API_KEY
```

You’ll see a success message and a pending status while it processes.

\*note that files can only be PDF, TXT, Markdown, CSV

<br />

### 5. Check the Voiceflow website

* Go to [app.voiceflow.com](https://creator.voiceflow.com/)
* Open your Agent project
* Click “Knowledge” in the sidebar to view the file
* You should see your newly updated file there

![image.png](attachment:d09d30cf-6376-4e2e-a4d7-09b793153e89:image.png)