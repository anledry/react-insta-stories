# react-insta-stories 💁‍♀️

> A React component for Instagram like stories

[![NPM](https://img.shields.io/npm/v/react-insta-stories.svg)](https://www.npmjs.com/package/react-insta-stories) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

![Demo screenshot](https://i.imgur.com/Twvjxp5.png)

## Install

```bash
npm install --save react-insta-stories
```

## Demo
⚡️ Video support added! Watch the demo below!

The component responds to actions like tap on right side for next story, on left for previous and tap and hold for pause. Custom time duration for each story can be provided.
See it in action here: https://mohitk05.github.io/react-insta-stories/

## Usage

```jsx
import React, { Component } from 'react'

import Stories from 'react-insta-stories'

class App extends Component {
  render () {
    return (
      <Stories 
        stories={stories}
        defaultInterval={1500}
        loader={<div>Loading...</div>}
        width={432}
        height={768}
      />
    )
  }
}

const stories = [
  'https://i.imgur.com/YA4fraZ.png', 
  'https://i.imgur.com/Ik635gD.jpg', 
  { url: 'https://i.imgur.com/mDuSAmB.png', duration: 1500 }, 
  { url: 'https://storage.googleapis.com/coverr-main/mp4/Footboys.mp4', type: 'video' },
  'https://www.jlstms.com/data/wallpapers/54/im58571310.jpg',
  'https://i.imgur.com/YA4fraZ.png'
]
```

## Props

#### _Update: Header added!_ 🤩

Property | Type | Default | Description
--- | --- | --- | ---
`stories` | [String/Object] | `required` | An array of image urls `['https://i.imgur.com/YA4fraZ.png', 'https://i.imgur.com/Ik635gD.jpg']` or array of story objects `[{ url: 'https://i.imgur.com/mDuSAmB.png', duration: 1500 }, { url: 'https://i.imgur.com/YA4fraZ.png', header: { heading: '@mohitk05', subheading: 'Posted 5h ago', profileImage: 'https://avatars0.githubusercontent.com/u/24852829?s=400&v=4' } }]`
`defaultInterval` | Number | 1200 | Milliseconds duration for which a story persists
`loader` | Component | 'Loading..' | A loader component as a fallback until image loads from url
`header` | Component | Default header as in demo | A header component which sits at the top of each story. It receives the `header` object from the `story` object. Data for header to be sent with each story object.
`width` | Number | 360 | Width of the component in pixels
`height` | Number | 640 | Height of the component in pixels

### Story object
Instead of simple string url, a comprehensive 'story object' can also be passed in the `stories` array.

Property | Description
--- | ---
`url` | The url of the resource, be it image or video.
`duration` | Optional. Duration for which a story should persist.
`header` | Optional. Adds a header on the top. Object with `heading`, `subheading` and `profileImage` properties.
`type` | Optional. To distinguish a video story. `type: 'video'` is necessary for a video story. 

## License

MIT © [mohitk05](https://github.com/mohitk05)
