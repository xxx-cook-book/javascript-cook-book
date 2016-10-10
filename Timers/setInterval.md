# setInterval

## Count Down

```javascript
setInterval(function() {
    refresh(started_stamp - new Date().valueOf())
}, 1);  // Normal

vs.

setInterval(function() {
    refresh(left_seconds--)
}, 1);  // Slow
```

## References

[1] Timers@W3C, [WD-html5-20110525](https://www.w3.org/TR/2011/WD-html5-20110525/timers.html)

[2] Docs@MDN, [WindowTimers.setInterval() — Repeatedly calls a function or executes a code snippet, with a fixed time delay between each call. Returns an `intervalID`.](https://developer.mozilla.org/en-US/docs/Web/API/WindowTimers/setInterval)

[3] Deniz Dogan@StackOverflow, [[Will setInterval drift?](http://stackoverflow.com/questions/985670/will-setinterval-drift)](http://stackoverflow.com/questions/985670/will-setinterval-drift)