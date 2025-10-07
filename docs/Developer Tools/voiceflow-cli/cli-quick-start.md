---
title: Quick start
deprecated: false
hidden: false
metadata:
  robots: index
---
`voiceflow-cli` is a command-line tool that allows Voiceflow users to [upload files to their knowledge base](doc:upload-files), [download transcripts](doc:fetching), [run automated tests](doc:automated-testing), and more.

In a few minutes, this guide will walk you through installing the CLI, authenticating your agent, and uploading a document to your [knowledge base](doc:knowledge-base).

<br />

## 1. Install the CLI

Open your terminal, then input the  command below that corresponds to your operating system. If you're on MacOS or Linux, [install brew before running this command](https://brew.sh/).

```curl Mac or Linux
brew install xavidop/tap/voiceflow
```
```text Windows
curl -sfL https://voiceflow.xavidop.me/static/run | bash
```

Alternatively, you can install the Voiceflow CLI via Chocolatey (Windows) or APT (Linux). [Click here to learn more.](doc:cli-install)

<br />

To check if the Voiceflow CLI was successfully installed, run:

```bash
voiceflow --help
```

You should see a list of commands, as shown below. If you do, the installation was successful - you're all set!!

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NSxkKo0EIimEag8BWSoQbTdFYpDN5wRPeli0j2" />

<br />

## 2. Grab your agent's API key

* Open the [Voiceflow Creator](https://creator.voiceflow.com/), and click the agent you want to use with the CLI.
* In the sidebar, click **Settings** → **API keys**
* Click the **copy** button to grab your API key

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NSgC3lEmcdtVY8pvMo6K2ksaDj0z4g5XZ7nI3h" />

<br />

<br />

## 3. Add the agent's API key to your environment

Run the following command, making sure you replace `YOUR_KEY` with the copied API key from the previous step. This will add your API key to the environment.

```Text bash
export VF_API_KEY=YOUR_KEY
```

Alternatively, you can authenticate using a flag, or a `.env` file. [Click here to learn more.](doc:authentication)

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NSsKfjoUzzvNuIPLsxO2KUc05GVE9RlySWktCi" />

<br />

## 4. Upload data to your agent's knowledge base

You're almost there! Finally, paste the following command into your terminal to upload data to your agent's knowledge base. In this example, we'll upload the contents of this page!

```bash
voiceflow document upload-url --url https://docs.voiceflow.com/docs/cli-quick-start.md --name "Quick Start"
```

While the upload processes, you'll see a pending status in your terminal.

To check if your data was successfully updated to the agent's knowledge base, go back to your Voiceflow project, and click **knowledge base** button in your sidebar. You should see your newly updated file as shown below.

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NSP20Noz7lF9by0OHwa4UL5XrKMoYGdeckgTqN" />

<br />

## Congratulations!

You just successfully installed the CLI, authenticated your agent, and uploaded your first document to the knowledge base. From here, you can explore the full range of CLI commands to test your agent, fetch transcripts, and automate your workflows. Happy building!
