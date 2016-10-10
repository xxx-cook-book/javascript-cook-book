# Copy Text Forbidden

## Javascript

```javascript
<script>
function stop() {
	return false;
}
document.oncontextmenu = stop;
document.ondragstart = stop;
document.onselectstart = stop;
document.onkeydown = function(e) {
	var ev = window.event || e;
	var code = ev.keyCode || ev.which;
	if (code == 116) {
		ev.keyCode ? ev.keyCode = 0 : ev.which = 0;
		cancelBubble = true;
		return false;
	}
}
</script>
```
## CSS

```css
<style type="text/css">
html {
	      -ms-user-select: none;
	    -moz-user-select: none;
	-webkit-user-select: none;
}
</style>
```
* Open Print Dialog

  ```css
  <style type="text/css">
  @media print {
  	html {
  		display: none;
  	}
  }
  </style>
  ```

## References