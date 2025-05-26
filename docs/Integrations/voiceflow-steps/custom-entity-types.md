---
title: Custom Entity Types
excerpt: Extract a Zip Code
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Sometimes you'll want to create your own entity type when the built-in options do not fit with the user reply you are expecting. 

In this video example, we will be creating an entity type that is specifically for zip codes. 

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FBA9EeICzzG4%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DBA9EeICzzG4&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FBA9EeICzzG4%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"640\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=BA9EeICzzG4&feature=youtu.be",
  "title": "Voiceflow - Custom Entity Types",
  "favicon": "https://www.youtube.com/s/desktop/ecd7151d/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/BA9EeICzzG4/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=BA9EeICzzG4&feature=youtu.be"
}
[/block]


**The RegEx Library**

You can find a number of other regular expressions to create your own entity types at <https://uibakery.io/regex-library>

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