# History Setting
At present, history has two modes: standard mode(for modern browsers) and compatible mode (for IE and old Edge).You can set history mode by `editor.config.compatibleMode` option.You aslo can set history max size by `editor.config.historyMaxSize` option.

when you set compatible mode, if you want to modify delay time for recording(when user is not active after x millisecond),
you can set it by `editor.config.onchangeTimeout` option. Here's an example:

```js
const E = window.wangEditor
const editor = new E("#div1")

// by default，IE and old Edge use compatible mode，if you want to set the mode for other browsers, you can set a function.
editor.config.compatibleMode = function () {
    // return true for compatible mode, otherwise return false for standard mode.
    return true
}

// when we use compatible mode, we can set frequency time for recording，the default value is 200 ms.
editor.config.onchangeTimeout = 500 // change to 500 ms

// you aslo can set max siz for history, the default value is 30.
editor.config.historyMaxSize = 50 // change to 50

editor.create()
```
