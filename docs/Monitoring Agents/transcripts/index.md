---
title: Transcripts
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
# Introduction to Transcripts on Voiceflow

You can get even more insights on each interaction with your prototype using the **Transcripts** functionality. You can access the Transcripts section by navigating to the main left panel located next to the sidebar.

The goal of the Transcripts is to give you and your team an understanding of where your assistant was successful in helping your users, and where it can be improved.

![](https://files.readme.io/1a16235-image.png)

Each transcript provides a turn-by-turn record of each user interaction, what utterances they used, and what intents they hit along the way.

It also allows you to collaborate with your team and stakeholders to provide **Actions**, **Tags** and **Notes** to help organize, enable and communicate information, all at the transcript-level.

# Saving a transcript

A transcript can be created from tests run on both the **Test Tool** (on the Creator Tool/Canvas) that you see as a designer, and on external tests run using **Sharable Prototype links**.

![](https://files.readme.io/0f5a47b-image.png)

## Saving in the Test Tool

For a session on the **Test Tool**, when the test ends, you will be shown an option to Save the test, and you can click that to save a transcript. 

![](https://files.readme.io/1c8ee0a-image.png)

You can also manually save a transcript at any point in the conversation by using the *Save Transcript* button in the Test Tool. On the Test Tool, transcripts are **not saved automatically**, so if you have an interesting conversation, make sure to click save.

![](https://files.readme.io/92a76c3-CleanShot_2024-06-24_at_15.04.592x.png)

## Saving in Sharable Prototypes

For tests run using the **Sharable Prototype**, each test's transcript will be saved **automatically**.

## Saving in Production

Interactions done in production (through the Dialog Manager API) aren't automatically saved. 

However, the out-of-the-box [web chat](https://developer.voiceflow.com/v2.0/docs/web-chat-overview) implements automatic transcript saving using the Transcripts API.  Your custom deployment can also save its transcripts easily with this API. Its docs can be found [here](https://developer.voiceflow.com/v2.0/reference/put_transcripts).

# Viewing, Sorting and Filtering Transcripts

Your transcripts can be found in the left-hand navigation, or quickly accessed using the keyboard shortcut 2.

Once in the **Transcripts** tab, you can click through all available transcripts for your assistant in the left-hand Conversations List.

![](https://files.readme.io/2eb54d9-CleanShot_2024-06-24_at_15.07.432x.png)

Navigating to the top of this list, you will find filters available to allow you to sort, organize & filter all of your available transcripts by date (**Time Range**) and by **Tags**.

This information can be added and adjusted at the transcript-level, using the right-hand Actions Menu.

![](https://files.readme.io/1162069-CleanShot_2024-06-24_at_15.08.442x.png)

You are also able to configure the type of data you'd like to view in the transcript, such as **debug messages** and **intent confidence data**. Using the ... menu above each transcript, you can choose to enable and disable these fields that you'd see in the Test Tool.

## Adding utterances to intents

If you have the Intent Confidence set to visible, you will see an option to "**Add utterance to intent**" on any utterance that did not match an intent during your testing. This is a quick way to use your test transcripts to **iterate on your design**, and improve your prototype's training. If you do add an utterance to an intent, it is important to remember to re-train your Assistant before testing again, to ensure it is trained with the new data.

![](https://files.readme.io/878f59c-CleanShot_2024-06-24_at_15.10.582x.png)

# Collaborating in Transcripts - Tagging and Commenting

How do you interact with team members on your user testing sessions?

As your team runs multiple tests and the transcripts screen gets filled with different tests, you can organize your transcripts with tags to make it easier for your team to sort through and find the important ones. In the right-hand Actions Menu, we offer built-in tags such as **Mark as Reviewed** and **Save for Later**. You can add your own custom tags by navigating and clicking into the **Tags** input field.

![](https://files.readme.io/96526a9-CleanShot_2024-06-24_at_15.14.132x.png)

Any tags you have created can be used to filter your **Conversations** (Transcripts) list.

In the **Add Tags** dropdown menu, you can select the **Manage Tags** option to **Delete** any tags from your assistant. You can also delete tags by hitting the **X** in the respective tag in the tag box.

You are also able to add notes or comments for designers and stakeholders to view in the **Notes** section under the **Tags** section.

# Managing Transcripts

Downloading and Deleting Transcripts. How to **export your user testing** sessions? How to **download or delete** user tests?

If you are looking to take your transcripts offline and off-tool or run further analysis on them, you have the option of exporting your transcript(s).

You can select the ... menu in the **Conversations** (Transcripts) list, located next to each transcripts' title, and click the **Export** option. This will download a CSV export of your transcript.

![](https://files.readme.io/cfc3ec5-CleanShot_2024-06-24_at_15.16.042x.png)

To delete irrelevant or undesired transcripts, you can select the **Delete** option from the ... menu, or from the right-hand **Actions** menu.
