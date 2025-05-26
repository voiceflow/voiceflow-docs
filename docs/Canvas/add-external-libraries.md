---
title: Add External Libraries
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
> ❗️ Recommended for testing and prototyping only
>
> We recommend users to move any advanced business logic that requires access to external libraries to a serverless function and use the API block to interact with it.

Sometimes you need to use one or more external libraries in a Code Step. Here is an example that uses the Day.js library and the Calendar plugin to transform a date.

In the example below we will translate an ISO formatted date to an easier to understand (human) version.

<Embed url="https://www.youtube.com/watch?v=p0e5FEAHITQ&feature=youtu.be" title="Voiceflow - Add External Libraries" favicon="https://www.youtube.com/s/desktop/ecd7151d/img/favicon.ico" image="https://i.ytimg.com/vi/p0e5FEAHITQ/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=p0e5FEAHITQ&feature=youtu.be" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252Fp0e5FEAHITQ%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253Dp0e5FEAHITQ%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252Fp0e5FEAHITQ%252Fhqdefault.jpg%26key%3D02466f963b9b4bb8845a05b53d3235d7%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

Here is the code used in the Code Step

```javascript
// Reset calendarDate value
calendarDate = '';

// Day.js doc > https://day.js.org/en/

// Require the Day.js library
const dayjs = requireFromUrl('https://unpkg.com/dayjs@1.10.7/dayjs.min.js');
// Require the DayJS Calendar plugin
const calendar = requireFromUrl('https://unpkg.com/dayjs@1.10.7/plugin/calendar.js')

// Extend Day.js with the Calendar plugin 
dayjs.extend(calendar)

// Format the response based on presets
calendarDate = dayjs(dayjs(theDate)).calendar(null, {
  sameDay: '[Today at] h:mm A', // The same day ( Today at 2:30 AM )
  nextDay: '[Tomorrow at] h:mm A', // The next day ( Tomorrow at 2:30 AM )
  nextWeek: 'dddd [at] h:mm A', // The next week ( Sunday at 2:30 AM )
  lastDay: '[Yesterday at] h:mm A', // The day before ( Yesterday at 2:30 AM )
  lastWeek: '[Last] dddd [at] h:mm A', // Last week ( Last Monday at 2:30 AM )
  sameElse: 'DD/MM/YYYY' // Everything else ( 17/10/2011 )
})
```
