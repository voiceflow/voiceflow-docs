---
title: Template Library
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
If you find yourself copy and pasting the same set of blocks again and again, and making minor changes to each copy of the set of blocks, you may want to try using a block template.

Block templates are reusable, changeable sequences of steps that make it simple to repeatedly duplicate generic structures. A template can contain either [a single block (with one or more steps)](https://developer.voiceflow.com/v2.0/docs/steps-blocks), or a larger flow with multiple blocks. Voiceflow provides a few starting templates as examples, with an API call, a basic conversation path, and a template to save information.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2ed9604-CleanShot_2024-06-19_at_14.45.49.gif",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


## Using templates

![](https://files.readme.io/a501eb2-CleanShot_2024-06-06_at_10.17.372x.png)

Templates are accessible through the Library tab on the left vertical step sidebar in the library tab (it's a library of all your templates).

You can simply drag out the name of one of these templates, and all the associated blocks and their connections will appear on the canvas just like any other step.

Once placed, the blocks in a template aren't related to the template any more, so changes to the template will not propagate to the blocks you got from the template. To repeat the same user flow again and again (same blocks without making changes), use a component step.

## Making your own template

To make your own template, select a single or a group of blocks.

![](https://files.readme.io/05cf626-CleanShot_2024-06-06_at_10.08.512x.png)

You can then right-click on your multi-selection and then click "Save to library". You can also customize the name and color of block templates.

![](https://files.readme.io/74bfb8d-CleanShot_2024-06-06_at_10.13.042x.png)