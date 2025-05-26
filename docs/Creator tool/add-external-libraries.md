---
title: Add External Libraries
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
[block:callout]
{
  "type": "danger",
  "title": "Recommended for testing and prototyping only",
  "body": "We recommend users to move any advanced business logic that requires access to external libraries to a serverless function and use the API block to interact with it."
}
[/block]
Sometimes you need to use one or more external libraries in a Code Step. Here is an example that uses the Day.js library and the Calendar plugin to transform a date.

In the example below we will translate an ISO formatted date to an easier to understand (human) version.
[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2Fp0e5FEAHITQ%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3Dp0e5FEAHITQ&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2Fp0e5FEAHITQ%2Fhqdefault.jpg&key=02466f963b9b4bb8845a05b53d3235d7&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=p0e5FEAHITQ&feature=youtu.be",
  "title": "Voiceflow - Add External Libraries",
  "favicon": "https://www.youtube.com/s/desktop/ecd7151d/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/p0e5FEAHITQ/hqdefault.jpg"
}
[/block]
Here is the code used in the Code Step
[block:code]
{
  "codes": [
    {
      "code": "// Reset calendarDate value\ncalendarDate = '';\n\n// Day.js doc > https://day.js.org/en/\n\n// Require the Day.js library\nconst dayjs = requireFromUrl('https://unpkg.com/dayjs@1.10.7/dayjs.min.js');\n// Require the DayJS Calendar plugin\nconst calendar = requireFromUrl('https://unpkg.com/dayjs@1.10.7/plugin/calendar.js')\n\n// Extend Day.js with the Calendar plugin \ndayjs.extend(calendar)\n\n// Format the response based on presets\ncalendarDate = dayjs(dayjs(theDate)).calendar(null, {\n  sameDay: '[Today at] h:mm A', // The same day ( Today at 2:30 AM )\n  nextDay: '[Tomorrow at] h:mm A', // The next day ( Tomorrow at 2:30 AM )\n  nextWeek: 'dddd [at] h:mm A', // The next week ( Sunday at 2:30 AM )\n  lastDay: '[Yesterday at] h:mm A', // The day before ( Yesterday at 2:30 AM )\n  lastWeek: '[Last] dddd [at] h:mm A', // Last week ( Last Monday at 2:30 AM )\n  sameElse: 'DD/MM/YYYY' // Everything else ( 17/10/2011 )\n})",
      "language": "javascript"
    }
  ]
}
[/block]