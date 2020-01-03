# electron-clipboard-watcher

Poll the system clipboard for changing text or image data.

## Install

`npm install --save electron-clipboard-watcher`

## Usage

Start polling the clipboard for changes.

Usage:

```js
const clipboardWatcher = require('electron-clipboard-watcher')

clipboardWatcher({
  // (optional) delay in ms between polls
  watchDelay: 1000,

  // handler for when image data is copied into the clipboard
  onImageChange: function (nativeImage) { ... },

  // handler for when text data is copied into the clipboard
  onTextChange: function (text) { ... },

  // (optional) Compares text to conditionally trigger `onTextChange`
  textHasChanged: function (newText, lastText) { ... },

  // (optional) Compares text to conditionally trigger `onImageChange`
  imageHasChanged: function (newImage, lastImage) { ... }
})
```

The `clipboardWatcher` function returns an object with a `stop()`
function which you can use to deactivate the polling:

```
const watcher = clipboardWatcher({ ... })
watcher.stop()
```

## License

MIT
