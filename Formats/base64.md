# Base64

## Canvas

Load the image into an Image-Object, paint it to a canvas and convert the canvas back to a dataURL.

## FileReader

Load the image as blob via XMLHttpRequest and use the FileReader API to convert it to a data URL.

* lacks in browser support
* has better compression
* works for other file types as well.

## References

[1] Coder_sLaY@StackOverflow, [How to convert image into base64 string using javascript](http://stackoverflow.com/questions/6150289/how-to-convert-image-into-base64-string-using-javascript)