jQuery    

使用：
* 下载文件放在网页同一目录，通过<script>标签引用文件    
* 通过<script src=""> 引用cdn 上的文件 
* 使用国内CDN上的JQuery 很大可能上从缓存中加载jQuery，减少网页加载时间。

语法：$(selector).action();
* $ difine jQuery;    
* selector 查询和查找HTML元素    
* action() 对查找到的元素执行的操作    
---
jQuery效果动画： 
显示隐藏：    
* hide()
* show()
* toggle() 

淡入淡出：    
* fadeIn()
* fadeOut()
* fadeToggle() 淡入淡出之间切换
* fadeTo()
* $(selector).fadeTo(speed,opacity,callback) // opacity&&speed 为必要参数，opacity = Math.random();

滑动：    
* slideDown() 
* slideUp()
* slideToggle()

<b>以上效果方法未特殊说明的都有speed 和 callback 两个可选参数，speed: fast,slow和毫秒 ,callback 为回调函数指明动画结束后执行的动作</b>

动画：
* $(selector).animate({params},speed,callback);
* {params}为必要参数，定义形成动画的CSS属性 ，属性名必须为Camel标记法书写padding-left -> paddingLeft
* 连续使用多个animate() 方法会依次调用完成动画，

停止动画：
* stop() 
* $(selector).stop(stopAll,goToEnd);
* stopAll 是否应该清除动画队列。默认false，停止当前动画效果，允许队列动画继续向下执行
* goToEnd 是否立即完成当前动画，默认false
- - - 
jQuery HTML

获得内容 :
* text() - 设置或返回所选元素的文本内容
* html() - 设置或返回所选元素的内容（包括 HTML 标记）
* val()  - 设置或返回表单字段的值
* attr() - 设置或返回所选元素的属性值 设置多个属性时attr({"prop":"value","prop":"value",...});

添加HTML内容：
* append() - 在被选元素内部的结尾插入指定内容
* prepend() - 在被选元素内部的开头插入指定内容
* after() - 在被选元素之后插入内容
* before() - 在被选元素之前插入内容
* append/prepend 是在选择元素内部嵌入，而after/before 是在元素外面追加。

删除元素：
* remove() - 删除被选元素（及其子元素）  可接受一个参数，允许您对被删元素进行过滤。该参数可以是任何 jQuery 选择器的语法。
* empty() - 从被选元素中删除子元素

操作CSS：
* addClass() - 向被选元素添加一个或多个类(多个类用空格分隔)
* removeClass() - 从被选元素删除一个或多个类
* toggleClass() - 对被选元素进行添加/删除类的切换操作
* css() - 设置或返回被选元素的一个或多个样式属性 css({"propertyname":"value","propertyname":"value",...});

尺寸：
* width() 设置或返回元素的宽度（不包括内边距、边框或外边距）
* height()
* innerWidth() 方法返回元素的宽度（包括内边距）
* innerHeight()
* outerWidth() 返回元素的宽度（包括内边距和边框）,outerWidth(true) 方法返回元素的宽度（包括内边距、边框和外边距）
* outerHeight()
- - -

