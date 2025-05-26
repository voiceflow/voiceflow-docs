---
title: Visual Response | Directive Step
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
Introduction
------------

In this article we will go over the use of the **Directive step** and the new Alexa **Response Builder** available on the **Alexa Developer Console**.

Context
-------

The **Alexa Developer Console** provide two ways of generating visual responses with **APL (**Alexa Presentation Language**)**.

- The Multimodal Response Builder
- The APL Authoring Tool (for advanced users)

For this project, we are going to use the **Multimodal Response Builder** with a template to build a video player.

What we need?
-------------

We will need a new **Alexa project** to upload to the **Alexa Developer Console**, a **Code step** and a **Conditions step** to check that the device support **APL** and a **Directive step** to display our **APL** document on the device.

***

### Step 1 | Create and link the APL document to your project

In Voiceflow, you will have to upload your Alexa project at least once to access it on the Alexa Developer Console.

After the upload go to the Alexa Developer Console ([\<\<https://developer.amazon.com/alexa/console/ask>>](https://developer.amazon.com/alexa/console/ask)), open your skill and go to the Build tab.

From the **Build** tab, expand the **Assets** section, click on **Multimodal Responses** and in the **Multimodal Responses** page, click the **Create Visual Response** button.

![](https://files.readme.io/1969e04-CleanShot_2022-08-17_at_14.46.19.png)

Choose the name you want on the modal window and click **Create**:

![](https://files.readme.io/85265f4-CleanShot_2022-08-17_at_14.49.27.png)

We want to create a video player so on the next screen, select the **Video** **Player** template:

![](https://files.readme.io/7ec301a-CleanShot_2022-08-17_at_14.50.23.png)

On the next screen you will be able to customize the template as you like, for this project we will use the defaults settings as we will be able to changes them within Voiceflow.

Click the **Next: Preview & Test** button to continue.

![](https://files.readme.io/7f20de4-CleanShot_2022-08-17_at_14.51.49.png)

On the last screen, you will be able to preview the template and even test it on any devices **supporting APL** and **registered to your developer account**.

![](https://files.readme.io/65de5a0-CleanShot_2022-08-17_at_15.07.49.png)

When you’re good, click on the **Done!** button.

![](https://files.readme.io/126f8bb-CleanShot_2022-08-17_at_15.09.40.png)

A summary screen will let you choose how you want to handle this APL document, for this project we will use the simplest way and click on **Integrate response to skill**.

![](https://files.readme.io/59d2755-CleanShot_2022-08-17_at_15.10.25.png)

Back on the Build page, choose **I’ll** **build** **later** on the modal view.

![](https://files.readme.io/c35a355-CleanShot_2022-08-17_at_15.13.45.png)

Last step before going back to the Voiceflow project, click on Copy code button to copy the Directive code will will use in the next step.

![](https://files.readme.io/64bd2c6-CleanShot_2022-08-17_at_15.25.10.png)

![](https://files.readme.io/684fe4f-CleanShot_2022-08-17_at_15.26.36.png)

### Step 2 | Setup the Directive step

On your Voiceflow Alexa project, drag a Directive step and link it to your Start step:

![](https://files.readme.io/d69443b-CleanShot_2022-08-17_at_15.28.03.png)

Paste the code from the Alexa Developer Console in the Directive step:

![](https://files.readme.io/8edecf0-CleanShot_2022-08-17_at_15.30.34.png)

To avoid the skill to end right after the Directive, we want to add:

```
shouldEndSession: null
```

To do so, we will use a Javascript step and put the following code:

```
_response = {
  shouldEndSession: null
}
```

![](https://files.readme.io/025ce8b-CleanShot_2022-08-17_at_18.42.59.png)

Now you can upload your project to **Alexa** so we can test it in the Alexa Developer Console

![](https://files.readme.io/889b0e2-CleanShot_2022-08-17_at_15.33.37.png)

![](https://files.readme.io/2ed50bc-CleanShot_2022-08-17_at_15.33.16.png)

### Step 3 | Activate APL interface and test on the Alexa Developer Console

Back on the **Alexa Developer Console**, be sure to be on the **Build tab**, expand the **Assets** section and click on **Interfaces**.

![](https://files.readme.io/4da2621-CleanShot_2022-08-17_at_15.34.58.png)

We want to activate the **Alexa Presentation Language** interface:

![](https://files.readme.io/d0fc58f-CleanShot_2022-08-17_at_15.38.44.gif)

Save your change by clicking on Save Interfaces button at the top of the page.

![](https://files.readme.io/a45da9c-CleanShot_2022-08-17_at_15.39.01.png)

![](https://files.readme.io/5a9667b-CleanShot_2022-08-17_at_15.40.32.png)

> 🚧 
> 
> You might need to wait around 3-5 minutes for the changes to populate before being able to fully test the skill.

Go to the **Test** tab, be sure to check the **Device Display** settings and run a test.

![](https://files.readme.io/60f426d-CleanShot_2022-08-17_at_18.47.04.png)

You should get a similar result, using the default template settings.

### Step 3 | Edit your template on ADC

As we are using a template integrated with our skill, you can edit it from the **Multimodal** **Responses** section on the **Build** tab to generate a new **directive code** we can paste into the **Directive step** in our Voiceflow project.

To do so, click on the **Edit In Response Builder** link.

![](https://files.readme.io/b168632-CleanShot_2022-08-17_at_18.49.54.png)

From the next screen, you can click on **Customize** to edit/update your APL template.

![](https://files.readme.io/62f39c8-CleanShot_2022-08-17_at_18.52.04.png)

Here for example, I’m updating the **Control** **Type** property

![](https://files.readme.io/9b7219a-CleanShot_2022-08-17_at_19.19.18.png)

You can tweak and change all the properties available but do not forget to click the** Next: Preview & Test **button and then on the Done! button when you’re done to populate your changes.

![](https://files.readme.io/a207b7d-CleanShot_2022-08-17_at_18.56.39.png)

![](https://files.readme.io/808ac21-CleanShot_2022-08-17_at_18.57.08.png)

On the **Congratulations**! screen, click on the **Integrate response to skill** button.

![](https://files.readme.io/1ffc22f-CleanShot_2022-08-17_at_18.59.37.png)

Back on the **Integrate** **response** **into** **skill** page, be sure to click on the **Build** **Model** button on the top right or on the **Build for me now** button on the modal to publish your changes to the linked document/template.

![](https://files.readme.io/aae65ce-CleanShot_2022-08-17_at_19.21.46.png)

![](https://files.readme.io/e99e2c4-CleanShot_2022-08-17_at_19.02.18.png)

We will also need to update our **directive** **code** so click on the **Copy** **code** button before going back to your **Voiceflow** **Alexa** **project**.

![](https://files.readme.io/2ac975e-CleanShot_2022-08-17_at_19.24.10.png)

### Step 4 | Update your template on Voiceflow

In your Voiceflow Alexa project, click on the **Directive** step and replace the actual code with the one you’ve just copied.

![](https://files.readme.io/e568391-CleanShot_2022-08-17_at_19.27.19.png)

Now that we have our base template, we can start tweaking the code in the directive as well.

To have a better view, click on the Expand Fullscreen button from the bottom right menu in the Directive step settings view.

![](https://files.readme.io/9fc911a-CleanShot_2022-08-17_at_19.28.38.png)

Let’s update the **headerTitle** value to use a variable we can populate before the Directive step to dynamically set a title.

![](https://files.readme.io/467637f-CleanShot_2022-08-17_at_19.31.13.png)

```javascript
"headerTitle": "{videoTitle}"
```

> 📘 
> 
> You can use **{variables}** in the **Directive** code anywhere you need them. As we’ve done for the **headerTitle** property, you can do the same with the **backgroundImage** for example.

As we are using a variable now we want to populate it with a value. We are using a Set step to do that.

![](https://files.readme.io/5a6b342-CleanShot_2022-08-17_at_19.36.49.png)

Upload you project to Alexa when you’re ready to test you changes.

> 🚧 
> 
> You might need to wait around 3-5 minutes for the changes to populate before being able to fully test the skill.

You should be able to see your changes (here the header title and the video control).

![](https://files.readme.io/d9df224-CleanShot_2022-08-17_at_20.08.15.png)

> 📘 Further reading
> 
> [Multimodal Response Builder](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-authoring-tool.html#use-mmrb)
> 
> [APL Authoring Tool](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-authoring-tool.html#use-auth-tool)
> 
> [Directives & Requests](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/what-makes-up-apl-visual-response.html#send-your-document-and-data-source-to-alexa)