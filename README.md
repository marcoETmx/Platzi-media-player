# Platzi Media Player

This is a plugin media player, you can:

- stop video automatically when user changes tabs
- stop video automatically when video jumps from user viewing area
- show advertising on the video from time to time
- automatic reproduction when the user enters the page

## Installation

You need node.js and npm. 

```bash
npm i @marcoetmx/mediaplayer
```

## Demo

You can visit demo [here](https://github.com/marcoETmx/ExampleMediaPlayer).

## Example

```typescript
import MediaPlayer from './MediaPlayer';
import AutoPlay from './plugins/AutoPlay'
import AutoPause from './plugins/AutoPause'
import Ads from './plugins/Ads'


const video = document.querySelector("video");
const button: HTMLElement = document.querySelector("#playButton");
const muteButton: HTMLElement = document.querySelector("#muteButton");


const player = new MediaPlayer({
    el: video, plugins: [
        new AutoPlay(), new AutoPause(), new Ads()
    ]
});
button.onclick = () => player.togglePlay();
muteButton.onclick = () => {
    if (player.media.muted) {

        player.unmute();
    } else {
        player.mute();
    }
}
```

### Notes

This project was created for educational purposes, it is not recommended to put it into production.