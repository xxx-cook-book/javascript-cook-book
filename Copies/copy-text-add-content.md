# Copy Text Add Content

## Selection(From Imooc)
*Ref: http://www.imooc.com/static/page/article/addCopy.js?v=201609281800*

```javascript
//获取作者&是否为原创信息
var $author = $('.aside-author').find('.nick').text();
var $original = $('.original').text();
// 复制追加内容
function addCopyright() {
    var Original = '</br>作者：'+$author+'</br>链接：' + location.href+'</br>来源：慕课网</br>'+$original;
    if ("function" == typeof window.getSelection) {
        var c = window.getSelection();
        if ("Microsoft Internet Explorer" == navigator.appName && navigator.appVersion.match(/MSIE ([\d.]+)/)[1] >= 10 || "Opera" == navigator.appName) {
            var g = c.getRangeAt(0),
            h = document.createElement("span");
            h.appendChild(g.cloneContents()),
            g.insertNode(h);
            var i = h.innerHTML.replace(/(?:\n|\r\n|\r)/gi, "").replace(/&lt;\s*script[^&gt;]*&gt;[\s\S]*?&lt;\/script&gt;/gim, "").replace(/&lt;\s*style[^&gt;]*&gt;[\s\S]*?&lt;\/style&gt;/gim, "").replace(/&lt;!--.*?--&gt;/gim, "").replace(/&lt;!DOCTYPE.*?&gt;/gi, "");
            try {
                document.getElementsByTagName("body")[0].removeChild(h)
            } catch(f) {
                h.style.display = "none",
                h.innerHTML = ""
            }
        } 
        var d = "" + c;
        var e = document.getElementsByTagName("body")[0],
        f = document.createElement("div");
        f.style.position = "absolute",
        f.style.left = "-99999px",
        e.appendChild(f),
        // f.innerHTML = d.replace(/([^&gt;\r\n]?)(\r\n|\n\r|\r|\n)/g, "$1&lt;br /&gt;$2") + "&lt;br /&gt;" + Original,
        f.innerHTML = d + Original,
        c.selectAllChildren(f),
        setTimeout(function() {
            e.removeChild(f)
        },
            0)
    } else if ("object" == typeof document.selection.createRange) {
        event.returnValue = !1;
        var c = document.selection.createRange().text;
        window.clipboardData.setData("Text", c + "\n" + Original)
    }
};
$('.detail-content').get(0).oncopy = addCopyright;
```

## References

[1] Selection@MDN, [A Selection object represents the range of text selected by the user or the current position of the caret.](https://developer.mozilla.org/en-US/docs/Web/API/Selection)
