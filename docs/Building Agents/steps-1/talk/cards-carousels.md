---
title: Card step and Carousel step
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
The **Card step** allows you to provide some on-screen information in-line with the conversational experience & interface, either on a screen-based device or on mobile, and can contain an image, title, description, and buttons. The **Carousel step** creates a carousel (like a gallery) of multiple cards, so works similarly.

*Note: Both the Card and Carousel steps are only available on chat assistants.*

# Card step

![](https://files.readme.io/89bf783-image.png)

## Card image

To get started with the Card step for chat assistants, ensure you navigate inside a Card step and have an intended image or GIF to upload into your design. The image upload is exactly the same for the [image](https://developer.voiceflow.com/v2.0/docs/images) step.

![](https://files.readme.io/9b85c86-image.png)

Once your Card image is uploaded, you will notice that the icon on the Card step canvas-view will update to your Card image preview.

## Card title and card description

You can also give your Card a *Title* and an associated *Description*. In each of these fields, you can also use variable(s) (using'**\{**' ) to make your card text fields more dynamic and personalized. And similar to Text steps, descriptions support markup styling.

## Adding Buttons to Cards

You can configure & add paths to your Cards and present the end-user with Buttons. You can click the (+) by the Buttons section to add Buttons and configure the Button label (with text or variables).

Cards support an unlimited number of buttons (though we recommend max 3-5).

Unlike the Button step, **Card buttons persist after the user’s initial interaction**. This means they will remain active, and the user may return to the Card during their session and make another selection. Otherwise, they should work identically to the standalone [Button step](https://developer.voiceflow.com/v2.0/docs/buttons).

![](https://files.readme.io/99c2afc-image.png)

A video breakdown of Cards can be found below:

<Embed url="https://www.youtube.com/watch?v=awK6AudHQU0" title="Intro to Voiceflow | Card Step - Visual Responses for your Chatbots (2022)" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/awK6AudHQU0/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=awK6AudHQU0" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FawK6AudHQU0%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DawK6AudHQU0%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FawK6AudHQU0%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

# Carousel step

![](https://files.readme.io/41d92d6-image.png)

The Carousel Step lets you display a selection or gallery of cards to your end users via a carousel or list.

Cards support multiple modalities and can be configured with any combination of image, title, description, and buttons. You can access the Carousel Step under the ‘Talk’ bucket in all custom Chat assistants.

## Configuring a Card

Once you’ve added a Carousel Step, add the elements you want displayed in your card. This process is similar to the Card step.

For Visuals, you can upload or link an image or GIF. Upon upload, a preview of your file will show in the editor and canvas. Variables can be added to the Title and Description for personalization. And similar to Text steps, descriptions support markup styling.

## Adding Buttons

You can configure & add paths/call-to-actions to your Cards and present the end-user with Buttons. You can click the (+) by the Buttons section to add Buttons and configure the Button label (with text or variables).

Cards support an unlimited number of buttons (though we recommend max 3-5). For now, card buttons can only be connected to conversation paths.

Unlike the Button Step, Carousel buttons persist after the user’s initial interaction. This means they will remain active, and the user may return to the Carousel during their session and make another selection.

You can use persistent Carousel buttons to ensure important information like disclaimers or privacy policies is always accessible to your users.

## Adding Multiple Cards

To add more cards and to provide a gallery/carousel view to your end users, hit ‘Add Card’. You’ll see a new template under your current card.

## Display Options

Cards can be displayed as horizontal carousels (default) or vertical lists. To change the orientation, open the step’s settings menu. Under ‘Buttons layout’, choose your desired option: Carousel or List.

## No Match/No Reply

You can also configure No Match or No Reply to handle scenarios where your user does not behave with your carousel as expected. To do so, open the step’s settings menu and select your desired No Match and/or No Reply. Learn more about [No Match](https://developer.voiceflow.com/v2.0/docs/no-match) and [No Reply](https://developer.voiceflow.com/v2.0/docs/no-reply-response).