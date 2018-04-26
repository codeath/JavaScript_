 **DOM**

文档对象模型（Document Object Model）：网页被加载时，由浏览器创建。定义了访问处理HTML文档的标准对象和标准方法    
HTML DOM TREE    
 ![htmltree](imgSrc/pic_htmltree.png)
 
 javascript DOM :    
 ![DOM知识脑图](imgSrc/1470709730442234.gif)

- - - 

* innerHTML - 修改HTML的内容 document.getElementById(id).innerHTML = new HTML ; 
* document.getElementById(id).style.property = new style; 改变CSS样式

HTML DOM EventListener:
* element.addEventListener(event,function,useCapture);
* 第一个参数是事件的类型 (如 "click" 或 "mousedown").
* 第二个参数是事件触发后调用的函数。
* 第三个参数是个布尔值用于描述事件是冒泡还是捕获。该参数是可选的。
* element.removeEventListenter(event,function); 用于移除addEventListener()添加的事件句柄    
*浏览器兼容版本：
var x = document.getElementById("myBtn"); 
if (x.addEventListener) {                    // 所有主流浏览器，除了 IE 8 及更早版本 
    x.addEventListener("click", myFunction); 
} else if (x.attachEvent) {                  // IE 8 及更早版本 
    x.attachEvent("onclick", myFunction); 
}*

事件传递有两种方式：冒泡与捕获。    
>事件传递定义了元素事件触发的顺序。 如果你将 &lt;p> 元素插入到 &lt;div> 元素中，用户点击 &lt;p> 元素, 哪个元素的 "click" 事件先被触发呢？    
>在冒泡中，内部元素的事件会先被触发，然后再触发外部元素，即： &lt;p> 元素的点击事件先触发，然后会触发 &lt;div> 元素的点击事件。        
>在捕获中，外部元素的事件会先被触发，然后才会触发内部元素的事件，即： &lt;div> 元素的点击事件先触发 ，然后再触发 &lt;p> 元素的点击事件。        
>addEventListener() 方法可以指定 "useCapture" 参数来设置传递类型：    
>addEventListener(event, function, useCapture);    
>默认值为 false, 即冒泡传递，当值为 true 时, 事件使用捕获传递。
---
JavaScript HTML DOM元素:        
在DOM中，每个节点都是一个对象。DOM节点有三个重要属性：    
<ol><li>nodeName:节点名称</li><li>nodeValue:节点值</li><li>nodeType:节点类型</li></ol>     
向HTML DOM 添加新元素，您必须首先创建该元素（元素节点），然后向一个已存在的元素追加该元素。

