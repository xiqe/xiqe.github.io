---
layout:     post
title:      利用postMessage解决iframe跨域通信
subtitle:   推荐两种实现方式，一为同域的页面代理，二为postMessage
date:       2019-03-01
author:     Jerry
header-img: img/post-bg-map.jpg
catalog: true
tags:
    - iframe高度自适应
    - 跨域
    - postMessage
    
---

# 前言
作为前端，我们经常会接触到的一种页面嵌套式形态就是iframe，而针对iframe最常见的需求点就是需要高度自适应，要解决这个问题，就必须使得父子页面之间可以进行通信。由于同源策略影响，跨域通信是最为棘手的存在。

目前有两种比较通用的方法可以支持。

# 方法一
页面A：http://www.a.com/iframe/a.html  
页面B：http://www.a.com/iframe/b.html  
页面C：http://www.iframe.com

页面A去iframe页面C

页面A
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset='utf-8' />
    <title>a.html</title>
  </head>
  <body>
    <iframe id="ifr" src="http://www.iframe.com" frameborder="0" width="100%"></iframe>
  </body>
</html>
```

页面B
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset='utf-8' />
    <title>b.html</title>
  </head>
  <body>
    <script type="text/javascript">
        window.onload = function() {
            var isSet = false;
            var inteval = setInterval(function() {
                var search = location.search.replace('?', '')
                if (isSet) {
                    clearInterval(inteval)
                    return  
                }
                if (search) {
                    var height = search.split('=')[1]
                    var doc = parent.parent.document
                    var ifr = doc.getElementById('ifr')
                    ifr.style.height = height + 'px'
                    isSet = true
                }
            }, 500)
        }
    </script>
  </body>
</html>
```

页面C
```html
<!doctype html>
<html>
<head>
    <title>http://www.iframe.com</title>
    <meta charset="utf-8">
</head>
<body>
    <h3>这是一个很长的页面，我要做跨域iframe的高度自适应</h3>
    <p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p>
    <iframe id="myiframe" style="display:none" src="http://www.a.com/iframe/b.html "></iframe>
    <script >
        function calcPageHeight(doc) {
            var cHeight = Math.max(doc.body.clientHeight, doc.documentElement.clientHeight)
            var sHeight = Math.max(doc.body.scrollHeight, doc.documentElement.scrollHeight)
            var height  = Math.max(cHeight, sHeight)
            return height
        }
        window.onload = function() {
            var doc = document
            var height = calcPageHeight(doc)
            var myiframe = doc.getElementById('myiframe')
            if (myiframe) {
                myiframe.src = 'http://www.a.com/iframe/b.html?height=' + height
            }
        };
    </script>
</body>
</html>
```

即A和C跨域，但是利用同域的B在C中进行代理，把C的高度丢给B，然后因为B和A同源，再把高度值传给A。


# 方法二
页面A：http://www.a.com/iframe/a.html  
页面C：http://www.iframe.com 

同样是页面A去iframe页面C

页面A
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset='utf-8' />
    <title>a.html</title>
  </head>
  <body>
    <iframe id="ifr" src="http://www.iframe.com" frameborder="0" width="100%"></iframe>
    <script>
        window.addEventListener("message", function( event ) {
            document.getElementById("ifr").style.height = event.data + 'px';
        }, false );
    </script>
  </body>
</html>
```

页面C
```html
<!doctype html>
<html>
<head>
    <title>http://www.iframe.com</title>
    <meta charset="utf-8">
</head>
<body>
    <h3>这是一个很长的页面，我要做跨域iframe的高度自适应</h3>
    <p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p><p>A</p>
    <iframe id="myiframe" style="display:none" src="http://www.a.com/iframe/b.html "></iframe>
    <script >
        function calcPageHeight(doc) {
            var cHeight = Math.max(doc.body.clientHeight, doc.documentElement.clientHeight)
            var sHeight = Math.max(doc.body.scrollHeight, doc.documentElement.scrollHeight)
            var height  = Math.max(cHeight, sHeight)
            return height
        }
        window.onload = function() {
            var doc = document
            var height = calcPageHeight(doc)
            top.postMessage(height,'*');  //出于安全考虑可以域的校验，在*处填写可以信任域
        };
    </script>
</body>
</html>
```

可以看到，方法二的实现更加的便捷，利用了HTML5的postMessage来处理跨域通信。

window.postMessage()方法被调用时，会在所有页面脚本执行完毕之后，向目标窗口派发一个``MessageEvent``消息。   
该MessageEvent消息有四个属性需要注意：
   
``message`` 属性表示该message的类型；  
``data`` 属性为 window.postMessage 的第一个参数；  
``origin`` 属性表示调用window.postMessage() 方法时调用页面的当前状态；   
``source`` 属性记录调用 window.postMessage() 方法的窗口信息。


如下是```MessageEvent```传递后的对象

```javascript
MessageEvent {
    bubbles: false
    cancelBubble: false
    cancelable: false
    composed: false
    currentTarget: Window {postMessage: ƒ, blur: ƒ, focus: ƒ, close: ƒ, parent: Window, …}
    data: 550   // data就是被传递的值
    defaultPrevented: false
    eventPhase: 0
    isTrusted: true
    lastEventId: ""
    origin: ""   // 出于安全考虑可以域的校验，数据规则的校验安全校验
    path: [Window]
    ports: []
    returnValue: true
    source: global {window: global, self: global, location: Location, closed: false, frames: global, …}
    srcElement: Window {postMessage: ƒ, blur: ƒ, focus: ƒ, close: ƒ, parent: Window, …}
    target: Window {postMessage: ƒ, blur: ƒ, focus: ƒ, close: ƒ, parent: Window, …}
    timeStamp: 216.3000000291504
    type: "message"
    __proto__: MessageEvent
}
```


