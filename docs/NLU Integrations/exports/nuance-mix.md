---
title: Nuance Mix - NLU Model Export
excerpt: Learn how to use our NLU export with Nuance Mix
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
[block:api-header]
{
  "title": "Quick Reference"
}
[/block]

[block:parameters]
{
  "data": {
    "0-0": "File format",
    "0-1": "XML",
    "1-0": "**Data Support**",
    "2-0": "Intents",
    "2-1": "✅",
    "3-1": "✅",
    "4-1": "✅",
    "5-1": "✅",
    "3-0": "Training Phrases",
    "4-0": "Entities",
    "5-0": "Synonyms",
    "6-0": "**Import Type** ",
    "7-0": "Modify",
    "7-1": "❌",
    "h-0": "Data",
    "h-1": "Support",
    "8-0": "Overwrite",
    "8-1": "✅"
  },
  "cols": 2,
  "rows": 9
}
[/block]

[block:api-header]
{
  "title": "Video Walkthrough"
}
[/block]

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2F6HvXyCFCpfY%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D6HvXyCFCpfY&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2F6HvXyCFCpfY%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=6HvXyCFCpfY&feature=youtu.be",
  "title": "Voiceflow NLU Export: Nuance Mix",
  "favicon": "https://www.youtube.com/s/desktop/01f7cad5/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/6HvXyCFCpfY/hqdefault.jpg"
}
[/block]

[block:api-header]
{
  "title": "Sample Export"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "<?xml version=\"1.0\" encoding=\"UTF-8\" standalone=\"yes\"?>\n<project xmlns:nuance=\"https://developer.nuance.com/mix/nlu/trsx\" xml:lang=\"en-US\" nuance:version=\"2.5\">\n  <metadata>\n    <entry key=\"short_name\">VF Burger</entry>\n    <entry key=\"source\">Voiceflow</entry>\n    <entry key=\"voiceflow_platform_type\">chatbot</entry>\n    <entry key=\"voiceflow_project_id\">62430560456f30001d59c471</entry>\n  </metadata>\n  <ontology>\n    <intents>\n      <intent name=\"place_order_3q9945n8\">\n        <links>\n          <link conceptref=\"sandwich_449h45os\"/>\n          <link conceptref=\"side_vr9o456k\"/>\n          <link conceptref=\"drink_dra045d9\"/>\n        </links>\n      </intent>\n    </intents>\n    <concepts>\n      <concept name=\"sandwich_449h45os\"/>\n      <concept name=\"side_vr9o456k\"/>\n      <concept name=\"drink_dra045d9\"/>\n    </concepts>\n  </ontology>\n  <dictionaries>\n    <dictionary conceptref=\"sandwich_449h45os\">\n      <entry literal=\"burger\" value=\"Hamburger\"/>\n      <entry literal=\"single\" value=\"Hamburger\"/>\n      <entry literal=\"plain burger\" value=\"Hamburger\"/>\n      <entry literal=\"Hamburger\" value=\"Hamburger\"/>\n      <entry literal=\"cheeseburg\" value=\"Cheeseburger\"/>\n      <entry literal=\"a cheeseburger\" value=\"Cheeseburger\"/>\n      <entry literal=\"cheese burger\" value=\"Cheeseburger\"/>\n      <entry literal=\"Cheeseburger\" value=\"Cheeseburger\"/>\n      <entry literal=\"chicken\" value=\"Super Chicken\"/>\n      <entry literal=\"chicken sandwich\" value=\"Super Chicken\"/>\n      <entry literal=\"Super Chicken\" value=\"Super Chicken\"/>\n      <entry literal=\"fish sandwich\" value=\"Fish Burger\"/>\n      <entry literal=\"fish filet\" value=\"Fish Burger\"/>\n      <entry literal=\"fish\" value=\"Fish Burger\"/>\n      <entry literal=\"Fish Burger\" value=\"Fish Burger\"/>\n      <entry literal=\"vegetable sandwich\" value=\"Veggie Burger\"/>\n      <entry literal=\"vegetarian sandwich\" value=\"Veggie Burger\"/>\n      <entry literal=\"veggie sandwich\" value=\"Veggie Burger\"/>\n      <entry literal=\"Veggie Burger\" value=\"Veggie Burger\"/>\n    </dictionary>\n    <dictionary conceptref=\"side_vr9o456k\">\n      <entry literal=\"fry\" value=\"Fries\"/>\n      <entry literal=\"a fries\" value=\"Fries\"/>\n      <entry literal=\"some fries\" value=\"Fries\"/>\n      <entry literal=\"french fries\" value=\"Fries\"/>\n      <entry literal=\"Fries\" value=\"Fries\"/>\n      <entry literal=\"gravy\" value=\"Poutine\"/>\n      <entry literal=\"fries and gravy\" value=\"Poutine\"/>\n      <entry literal=\"Poutine\" value=\"Poutine\"/>\n      <entry literal=\"onion\" value=\"Onion Rings\"/>\n      <entry literal=\"rings\" value=\"Onion Rings\"/>\n      <entry literal=\"onions\" value=\"Onion Rings\"/>\n      <entry literal=\"Onion Rings\" value=\"Onion Rings\"/>\n      <entry literal=\"Salad\" value=\"Salad\"/>\n    </dictionary>\n    <dictionary conceptref=\"drink_dra045d9\">\n      <entry literal=\"coca cola\" value=\"Coke\"/>\n      <entry literal=\"pepsi\" value=\"Coke\"/>\n      <entry literal=\"Coke\" value=\"Coke\"/>\n      <entry literal=\"seven up\" value=\"Sprite\"/>\n      <entry literal=\"7 up\" value=\"Sprite\"/>\n      <entry literal=\"Sprite\" value=\"Sprite\"/>\n      <entry literal=\"barks\" value=\"Root Beer\"/>\n      <entry literal=\"barks root beer\" value=\"Root Beer\"/>\n      <entry literal=\"barqs\" value=\"Root Beer\"/>\n      <entry literal=\"Root Beer\" value=\"Root Beer\"/>\n      <entry literal=\"cold tea\" value=\"Iced Tea\"/>\n      <entry literal=\"nestea\" value=\"Iced Tea\"/>\n      <entry literal=\"Iced Tea\" value=\"Iced Tea\"/>\n      <entry literal=\"Water\" value=\"Water\"/>\n    </dictionary>\n  </dictionaries>\n  <samples>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      <annotation conceptref=\"drink_dra045d9\">Coke</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      <annotation conceptref=\"side_vr9o456k\">Fries</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">I'd like to order a combo</sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      <annotation conceptref=\"sandwich_449h45os\">Hamburger</annotation>\n      with\n      <annotation conceptref=\"side_vr9o456k\">fry</annotation>\n      and a\n      <annotation conceptref=\"drink_dra045d9\">coca cola</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      need a\n      <annotation conceptref=\"sandwich_449h45os\">burger</annotation>\n      and a\n      <annotation conceptref=\"side_vr9o456k\">a fries</annotation>\n      and a\n      <annotation conceptref=\"drink_dra045d9\">pepsi</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      My order is\n      <annotation conceptref=\"sandwich_449h45os\">single</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      I want a\n      <annotation conceptref=\"sandwich_449h45os\">plain burger</annotation>\n      with\n      <annotation conceptref=\"drink_dra045d9\">Sprite</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      <annotation conceptref=\"sandwich_449h45os\">Cheeseburger</annotation>\n      please\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      <annotation conceptref=\"sandwich_449h45os\">cheeseburg</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      Give me a\n      <annotation conceptref=\"sandwich_449h45os\">a cheeseburger</annotation>\n      and\n      <annotation conceptref=\"side_vr9o456k\">some fries</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      I'd like to order a\n      <annotation conceptref=\"sandwich_449h45os\">cheese burger</annotation>\n      with\n      <annotation conceptref=\"side_vr9o456k\">french fries</annotation>\n      and a\n      <annotation conceptref=\"drink_dra045d9\">seven up</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      <annotation conceptref=\"sandwich_449h45os\">Super Chicken</annotation>\n      with\n      <annotation conceptref=\"side_vr9o456k\">Poutine</annotation>\n      and a\n      <annotation conceptref=\"drink_dra045d9\">7 up</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      need a\n      <annotation conceptref=\"sandwich_449h45os\">chicken</annotation>\n      and a\n      <annotation conceptref=\"side_vr9o456k\">gravy</annotation>\n      and a\n      <annotation conceptref=\"drink_dra045d9\">Root Beer</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      I want a\n      <annotation conceptref=\"sandwich_449h45os\">chicken sandwich</annotation>\n      with\n      <annotation conceptref=\"drink_dra045d9\">barks</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      I'd like to order a\n      <annotation conceptref=\"sandwich_449h45os\">Fish Burger</annotation>\n      with\n      <annotation conceptref=\"side_vr9o456k\">fries and gravy</annotation>\n      and a\n      <annotation conceptref=\"drink_dra045d9\">barks root beer</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      <annotation conceptref=\"drink_dra045d9\">barqs</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      <annotation conceptref=\"sandwich_449h45os\">fish sandwich</annotation>\n      with\n      <annotation conceptref=\"side_vr9o456k\">Onion Rings</annotation>\n      and a\n      <annotation conceptref=\"drink_dra045d9\">Iced Tea</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      need a\n      <annotation conceptref=\"sandwich_449h45os\">fish filet</annotation>\n      and a\n      <annotation conceptref=\"side_vr9o456k\">onion</annotation>\n      and a\n      <annotation conceptref=\"drink_dra045d9\">cold tea</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      I want a\n      <annotation conceptref=\"sandwich_449h45os\">fish</annotation>\n      with\n      <annotation conceptref=\"drink_dra045d9\">nestea</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      I'd like to order a\n      <annotation conceptref=\"sandwich_449h45os\">Veggie Burger</annotation>\n      with\n      <annotation conceptref=\"side_vr9o456k\">rings</annotation>\n      and a\n      <annotation conceptref=\"drink_dra045d9\">Water</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      <annotation conceptref=\"side_vr9o456k\">onions</annotation>\n    </sample>\n    <sample intentref=\"place_order_3q9945n8\" count=\"1\">\n      <annotation conceptref=\"sandwich_449h45os\">vegetable sandwich</annotation>\n      with\n      <annotation conceptref=\"side_vr9o456k\">Salad</annotation>\n      and a\n      <annotation conceptref=\"drink_dra045d9\">pepsi</annotation>\n    </sample>\n  </samples>\n</project>",
      "language": "xml",
      "name": "project_burger.xml"
    }
  ]
}
[/block]