---
title: Text
excerpt: ''
deprecated: true
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
**What is a Text Step? How do I respond to my user or make my chatbot type?**

The Text Step are the text messages shown in chat for all **Chat Assistants**, found in the **Talk** section of the **Steps** Menu. These are the text-responses your chat assistant/chatbot would respond back to your end-user.

A text step is important for the assistant to communicate to the user with words. It can be used to greet the user, ask questions, give instructions, and inform users. You can add text markup, manually create different versions of the same text step by adding variants, and use curly braces "{}" to reference assistant variable values. 

To configure your **Text Step**, you can type what you want your assistant to respond/display to your user in the text input field. 

![](https://files.readme.io/999c18d-CleanShot_2024-06-14_at_15.24.272x.png)

## Adding Markdown & Message Delay

For Chat Assistants, you can design **formatted text** responses using the Text Step and Markdown syntax.

You can style your text formatting using the **Bold**, _Italics_, Underline and ~~Strikethrough~~ options provided. Additionally, you can embed a [hyperlink](<>) in your text! These options are all available in the editor options under the text editor.

_Hyperlinking allows your assistant to have functionality such as opening a URL, calendar link, mail to, phone call and many more!_

You can also configure Message Delay (measured in MS) by clicking the icon at the right-most of the Text editor menu.

## Adding Variants

Adding variations in your text response steps allow for a more unique and natural conversation.

Variants are variations of the text greeting/response steps that the user expects to receive in the specific section of your conversation experience. If you have variants added to your Text Step, one of the variants will be **displayed at random** when the step is hit in your assistant.

You can add a variant to the Text Step by clicking the **Add Variant** button in the editor's footer. If you have variants added to your Text Step, one of the variants will be played at random when the step is hit in your assistant.

## Visual-View of Variants on Canvas

Once your variants are confirmed, you will notice that you can also visually preview them from the Canvas-level. By default, your variants will nest under a preview modal, with the dice icon appearing in the Text step. In this modal, you can quickly edit or copy those responses.

To instead display all the variants (as opposed to the preview view), you can change your Canvas Visibility setting under the settings icon located to the left of the Add Variant section in the Speak Step menu. You can toggle between show preview and show all variants, while also setting which option you desire as the default for all your text steps on Canvas.

![](https://files.readme.io/7e4d871-CleanShot_2024-06-14_at_15.35.292x.png)