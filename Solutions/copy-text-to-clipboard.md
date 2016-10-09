# Copy Text to Clipboard

## zClip

zClip is a lightweight jQuery "copy to clipboard" plugin built using the popular Zero Clipboard library. This plugin uses an invisible Adobe Flash movie that is fully.

## clipboard.js

This library relies on both [Selection](https://developer.mozilla.org/en-US/docs/Web/API/Selection) and [execCommand](https://developer.mozilla.org/en-US/docs/Web/API/Document/execCommand) APIs. The second one is supported in the following browsers.

| <img src="https://clipboardjs.com/assets/images/chrome.png" width="48px" height="48px" alt="Chrome logo"> | <img src="https://clipboardjs.com/assets/images/edge.png" width="48px" height="48px" alt="Edge logo"> | <img src="https://clipboardjs.com/assets/images/firefox.png" width="48px" height="48px" alt="Firefox logo"> | <img src="https://clipboardjs.com/assets/images/ie.png" width="48px" height="48px" alt="Internet Explorer logo"> | <img src="https://clipboardjs.com/assets/images/opera.png" width="48px" height="48px" alt="Opera logo"> | <img src="https://clipboardjs.com/assets/images/safari.png" width="48px" height="48px" alt="Safari logo"> |
|:---:|:---:|:---:|:---:|:---:|:---:|
| 42+ ✔ | 12+ ✔ | 41+ ✔ | 9+ ✔ | 29+ ✔ | 10+ ✔ |

Although copy/cut operations with [execCommand](https://developer.mozilla.org/en-US/docs/Web/API/Document/execCommand) aren't supported on Safari yet (including mobile), it gracefully degrades because [Selection](https://developer.mozilla.org/en-US/docs/Web/API/Selection) is supported.

That means you can show a tooltip saying `Copied!` when `success` event is called and `Press Command+C to copy` when `error` event is called because the text is already selected.

## References

[1] zClip@TT4IT, [zClip — a lightweight jQuery "copy to clipboard" plugin built using the popular Zero Clipboard library. This plugin uses an invisible Adobe Flash movie that is fully ](http://tt4it.com/exchange/blog/discuss/130/)

[2] clipboard.js@TT4IT, [clipboard.js —  A modern approach to copy text to clipboard. No Flash. No frameworks. Just 3kb gzipped](http://tt4it.com/resources/discuss/2325/)

[3] Docs@MDN, [Document.execCommand()](https://developer.mozilla.org/en-US/docs/Web/API/Document/execCommand)