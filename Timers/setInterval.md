# setInterval

## CountDown

```javascript
setInterval(function() {
    refresh(started_stamp - new Date().valueOf())
}, 1);  // Normal

vs.

setInterval(function() {
    refresh(left_seconds--)
}, 1);  // Slow
```

* Reasons for delays longer than specified

  There are a number of reasons why a timeout may take longer to fire than anticipated. This section describes the most common reasons.

  * Nested timeouts forced to >=4ms
    * Historically browsers implement setTimeout() "clamping": successive setTimeout() calls with delay smaller than the "minimum delay" limit are forced to use at least the minimum delay. The minimum delay, DOM_MIN_TIMEOUT_VALUE, is 4 ms (stored in a preference in Firefox: dom.min_timeout_value), with a DOM_CLAMP_TIMEOUT_NESTING_LEVEL of 5.
    * In fact, 4 ms is specified by the HTML5 spec and is consistent across browsers released in 2010 and onward. Prior to (Firefox 5.0 / Thunderbird 5.0 / SeaMonkey 2.2), the minimum timeout value for nested timeouts was 10 ms.
    * To implement a 0 ms timeout in a modern browser, you can use window.postMessage() as described here.


## References

[1] API@MDN, [WindowTimers.setInterval()](https://developer.mozilla.org/en-US/docs/Web/API/WindowTimers/setInterval)