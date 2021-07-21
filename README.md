This is related to [Chromium bug 1230120](https://bugs.chromium.org/p/chromium/issues/detail?id=1230120) which I reported on July 16, 2021. I discovered it as I was working on my first browser extension.

To reproduce this issue on `Chromium 91.0.4472.114 (Official Build) Arch Linux (64-bit)`, [load the extension](https://developer.chrome.com/docs/extensions/mv3/getstarted/) in this repo. Open the extension popup in Chrome, and observe that "Hello, World!" is not visible despite the body width having been updated to support the media query's minimum width of '400px'. Apparently, media queries aren't acknowledged by the dynamically updated width from the JavaScript loaded by the popup document. It's expected for the popup.html extension markup to respond to window media queries when styling the document, and for the "Hello, World!" text in `popup.html` to be visible.

This issue was fixed in `92.0.4515.107 (Official Build) Arch Linux (64-bit)`.
