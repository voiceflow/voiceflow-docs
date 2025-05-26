---
title: Nuance Mix - NLU Model Export
excerpt: Learn how to use our NLU export with Nuance Mix
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Quick Reference

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Data
      </th>

      <th style={{ textAlign: "left" }}>
        Support
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        File format
      </td>

      <td style={{ textAlign: "left" }}>
        XML
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **Data Support**
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Intents
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Training Phrases
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Entities
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Synonyms
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **Import Type** 
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Modify
      </td>

      <td style={{ textAlign: "left" }}>
        ❌
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Overwrite
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>
  </tbody>
</Table>

## Video Walkthrough

<Embed url="https://www.youtube.com/watch?v=6HvXyCFCpfY&feature=youtu.be" title="Voiceflow NLU Export: Nuance Mix" favicon="https://www.youtube.com/s/desktop/01f7cad5/img/favicon.ico" image="https://i.ytimg.com/vi/6HvXyCFCpfY/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=6HvXyCFCpfY&feature=youtu.be" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252F6HvXyCFCpfY%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253D6HvXyCFCpfY%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252F6HvXyCFCpfY%252Fhqdefault.jpg%26key%3Df2aa6fc3595946d0afc3d76cbbd25dc3%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## Sample Export

```xml project_burger.xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<project xmlns:nuance="https://developer.nuance.com/mix/nlu/trsx" xml:lang="en-US" nuance:version="2.5">
  <metadata>
    <entry key="short_name">VF Burger</entry>
    <entry key="source">Voiceflow</entry>
    <entry key="voiceflow_platform_type">chatbot</entry>
    <entry key="voiceflow_project_id">62430560456f30001d59c471</entry>
  </metadata>
  <ontology>
    <intents>
      <intent name="place_order_3q9945n8">
        <links>
          <link conceptref="sandwich_449h45os"/>
          <link conceptref="side_vr9o456k"/>
          <link conceptref="drink_dra045d9"/>
        </links>
      </intent>
    </intents>
    <concepts>
      <concept name="sandwich_449h45os"/>
      <concept name="side_vr9o456k"/>
      <concept name="drink_dra045d9"/>
    </concepts>
  </ontology>
  <dictionaries>
    <dictionary conceptref="sandwich_449h45os">
      <entry literal="burger" value="Hamburger"/>
      <entry literal="single" value="Hamburger"/>
      <entry literal="plain burger" value="Hamburger"/>
      <entry literal="Hamburger" value="Hamburger"/>
      <entry literal="cheeseburg" value="Cheeseburger"/>
      <entry literal="a cheeseburger" value="Cheeseburger"/>
      <entry literal="cheese burger" value="Cheeseburger"/>
      <entry literal="Cheeseburger" value="Cheeseburger"/>
      <entry literal="chicken" value="Super Chicken"/>
      <entry literal="chicken sandwich" value="Super Chicken"/>
      <entry literal="Super Chicken" value="Super Chicken"/>
      <entry literal="fish sandwich" value="Fish Burger"/>
      <entry literal="fish filet" value="Fish Burger"/>
      <entry literal="fish" value="Fish Burger"/>
      <entry literal="Fish Burger" value="Fish Burger"/>
      <entry literal="vegetable sandwich" value="Veggie Burger"/>
      <entry literal="vegetarian sandwich" value="Veggie Burger"/>
      <entry literal="veggie sandwich" value="Veggie Burger"/>
      <entry literal="Veggie Burger" value="Veggie Burger"/>
    </dictionary>
    <dictionary conceptref="side_vr9o456k">
      <entry literal="fry" value="Fries"/>
      <entry literal="a fries" value="Fries"/>
      <entry literal="some fries" value="Fries"/>
      <entry literal="french fries" value="Fries"/>
      <entry literal="Fries" value="Fries"/>
      <entry literal="gravy" value="Poutine"/>
      <entry literal="fries and gravy" value="Poutine"/>
      <entry literal="Poutine" value="Poutine"/>
      <entry literal="onion" value="Onion Rings"/>
      <entry literal="rings" value="Onion Rings"/>
      <entry literal="onions" value="Onion Rings"/>
      <entry literal="Onion Rings" value="Onion Rings"/>
      <entry literal="Salad" value="Salad"/>
    </dictionary>
    <dictionary conceptref="drink_dra045d9">
      <entry literal="coca cola" value="Coke"/>
      <entry literal="pepsi" value="Coke"/>
      <entry literal="Coke" value="Coke"/>
      <entry literal="seven up" value="Sprite"/>
      <entry literal="7 up" value="Sprite"/>
      <entry literal="Sprite" value="Sprite"/>
      <entry literal="barks" value="Root Beer"/>
      <entry literal="barks root beer" value="Root Beer"/>
      <entry literal="barqs" value="Root Beer"/>
      <entry literal="Root Beer" value="Root Beer"/>
      <entry literal="cold tea" value="Iced Tea"/>
      <entry literal="nestea" value="Iced Tea"/>
      <entry literal="Iced Tea" value="Iced Tea"/>
      <entry literal="Water" value="Water"/>
    </dictionary>
  </dictionaries>
  <samples>
    <sample intentref="place_order_3q9945n8" count="1">
      <annotation conceptref="drink_dra045d9">Coke</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      <annotation conceptref="side_vr9o456k">Fries</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">I'd like to order a combo</sample>
    <sample intentref="place_order_3q9945n8" count="1">
      <annotation conceptref="sandwich_449h45os">Hamburger</annotation>
      with
      <annotation conceptref="side_vr9o456k">fry</annotation>
      and a
      <annotation conceptref="drink_dra045d9">coca cola</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      need a
      <annotation conceptref="sandwich_449h45os">burger</annotation>
      and a
      <annotation conceptref="side_vr9o456k">a fries</annotation>
      and a
      <annotation conceptref="drink_dra045d9">pepsi</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      My order is
      <annotation conceptref="sandwich_449h45os">single</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      I want a
      <annotation conceptref="sandwich_449h45os">plain burger</annotation>
      with
      <annotation conceptref="drink_dra045d9">Sprite</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      <annotation conceptref="sandwich_449h45os">Cheeseburger</annotation>
      please
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      <annotation conceptref="sandwich_449h45os">cheeseburg</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      Give me a
      <annotation conceptref="sandwich_449h45os">a cheeseburger</annotation>
      and
      <annotation conceptref="side_vr9o456k">some fries</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      I'd like to order a
      <annotation conceptref="sandwich_449h45os">cheese burger</annotation>
      with
      <annotation conceptref="side_vr9o456k">french fries</annotation>
      and a
      <annotation conceptref="drink_dra045d9">seven up</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      <annotation conceptref="sandwich_449h45os">Super Chicken</annotation>
      with
      <annotation conceptref="side_vr9o456k">Poutine</annotation>
      and a
      <annotation conceptref="drink_dra045d9">7 up</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      need a
      <annotation conceptref="sandwich_449h45os">chicken</annotation>
      and a
      <annotation conceptref="side_vr9o456k">gravy</annotation>
      and a
      <annotation conceptref="drink_dra045d9">Root Beer</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      I want a
      <annotation conceptref="sandwich_449h45os">chicken sandwich</annotation>
      with
      <annotation conceptref="drink_dra045d9">barks</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      I'd like to order a
      <annotation conceptref="sandwich_449h45os">Fish Burger</annotation>
      with
      <annotation conceptref="side_vr9o456k">fries and gravy</annotation>
      and a
      <annotation conceptref="drink_dra045d9">barks root beer</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      <annotation conceptref="drink_dra045d9">barqs</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      <annotation conceptref="sandwich_449h45os">fish sandwich</annotation>
      with
      <annotation conceptref="side_vr9o456k">Onion Rings</annotation>
      and a
      <annotation conceptref="drink_dra045d9">Iced Tea</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      need a
      <annotation conceptref="sandwich_449h45os">fish filet</annotation>
      and a
      <annotation conceptref="side_vr9o456k">onion</annotation>
      and a
      <annotation conceptref="drink_dra045d9">cold tea</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      I want a
      <annotation conceptref="sandwich_449h45os">fish</annotation>
      with
      <annotation conceptref="drink_dra045d9">nestea</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      I'd like to order a
      <annotation conceptref="sandwich_449h45os">Veggie Burger</annotation>
      with
      <annotation conceptref="side_vr9o456k">rings</annotation>
      and a
      <annotation conceptref="drink_dra045d9">Water</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      <annotation conceptref="side_vr9o456k">onions</annotation>
    </sample>
    <sample intentref="place_order_3q9945n8" count="1">
      <annotation conceptref="sandwich_449h45os">vegetable sandwich</annotation>
      with
      <annotation conceptref="side_vr9o456k">Salad</annotation>
      and a
      <annotation conceptref="drink_dra045d9">pepsi</annotation>
    </sample>
  </samples>
</project>
```
