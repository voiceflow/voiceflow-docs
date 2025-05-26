---
title: Custom Entity Types
excerpt: Extract a Zip Code
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Sometimes you'll want to create your own entity type when the built-in options do not fit with the user reply you are expecting. 

In this video example, we will be creating an entity type that is specifically for zip codes. 

<Embed url="https://www.youtube.com/watch?v=BA9EeICzzG4&feature=youtu.be" title="Voiceflow - Custom Entity Types" favicon="https://www.youtube.com/s/desktop/ecd7151d/img/favicon.ico" image="https://i.ytimg.com/vi/BA9EeICzzG4/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=BA9EeICzzG4&feature=youtu.be" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FBA9EeICzzG4%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DBA9EeICzzG4%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FBA9EeICzzG4%252Fhqdefault.jpg%26key%3Df2aa6fc3595946d0afc3d76cbbd25dc3%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22640%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

**The RegEx Library**

You can find a number of other regular expressions to create your own entity types at [https://uibakery.io/regex-library](https://uibakery.io/regex-library)

**Here is the code used in the Code Step** 

```javascript
errorMessage = 0;

// Extract zip code from a string
var zipRegexG = /[0-9]{5}(?:-[0-9]{4})?/g;

try {
    zipcode = zipcode.match(zipRegexG)[0];
}
  catch(e) {
    errorMessage = "Looks like it's not a zipcode" // or e.message;
}
```
