# Note-for-JS-Event
To make some notes about JS Event
##事件类型
1. UI事件
2. 焦点事件
3. 鼠标事件
4. 滚轮事件
5. 文本事件
6. 键盘事件
7. 合成事件
8. H5事件
9. 手势事件

##UI事件
###load事件

EventUtil:

```javascript
  EventUtil.addHandler(window, "load", function(event){
      ***relative code***
  });
```
DOM 0 级 <body>:

```javascript
<body onload=function(event){
     ***relative code***
}>
```

适用对象:

\<img\>：当设置了src属性后才会开始下载， ！先指定事件处理程序再设置src属性

\<script\>：当设置了src睡醒并将该元素添加到文档后才会开始下载 ！指定src属性和事件处理程序的顺序不重要

\<link\>：同\<script\>

###unload事件

EventUtil：同load事件

DOM 0 级：同load事件

触发条件：用户从一个页面切换到另一个页面
用途：清除引用，避免内存泄露
注意事项： unload事件触发后，原页面加载后存在的那些对象已经不复存在，操作DOM节点或元素式样会导致报错

###resize事件

EventUtil：同上

DOM 0 级：同上

触发条件：IE、Safari、Chrome和Opera会在浏览器窗口变化了1px时触发，然后随着变化不断触发
                     Firefox只在用户停止调整窗口大小时触发
        
注意事项：事件处理程序谨慎加入大计算量代码，该事件处理程序会被频繁执行

###scroll事件

EventUtil：

```javascript
EventUtil.addHandler(window, "scroll", function(event){
      if (document.compatMode == "CSS1Compat"){
            alert(document.documentElement.scrollTop); #混杂模式
            ***relative code***
      } else {
            alert(document.body.scrollTop); #标准模式（Safari）
            ***relative code***
      }
});
```

DOM 0 级：同上， 由于推荐使用javascript方式，故不再列举DOM方式

 触发条件： 页面滚动
 
 注意事项： 同resize事件
 
 
##焦点事件
用途：利用焦点事件与document.hasFocus()和document.activeElement配合，可知晓用户在页面上的行踪
###blur事件
HTML事件，在元素失去焦点时触发，但是不会冒泡；所有浏览器支持它

###focus事件
HTML事件，在元素获得焦点时触发，但是不会冒泡；所有浏览器支持它

###focusout事件
DOM 3 级事件，在元素失去焦点时触发，为focus事件的通用版本，但是冒泡，主流浏览器支持该事件

###focusin事件
DOM 3 级事件，在元素获得焦点时触发，为blur事件的通用版本，但是冒泡，主流浏览器支持该事件

###DOMFocusout事件
在元素失去焦点时触发，为focus事件的通用版本，但是冒泡，被DOM 3 级废弃，仅Opera浏览器支持

###DOMFocusin事件
在元素获得焦点时触发，为focus事件的通用版本，但是冒泡，被DOM 3 级废弃，仅Opera浏览器支持


