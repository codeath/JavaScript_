<b>Door of JS</b>

<b>数据类型</b>    
Number：JS不区分整数和浮点数，统一表示（Number）；
<pre><code>
123;//整数123
0.456;//浮点数
1.234e3;//科学计数1.234 X 1000
-99;//负数
NaN;//not a number，无法计算结果
Infinity;//数值超过JS的Number所能表示的最大值，
</code></pre>

字符串：JS中用''和""括起来的任意文本表示(ES6 支持``表示多行字符串，否则用\n)       
* 模板字符串  var message= 'Hello!' + name + ',you are ' + age +'years old!';        
* ES6        var message = 'Hello!${name},you are ${age} years old!';    
* 字符串是不可变的，对字符串的某个索引赋值，不会有任何效果，但也没有任何错误    
          
布尔值：布尔值和布尔代数表示完全一致，只有（true 和 false）     

比较运算符：JS允许对任意数据类型做比较           
* false == 0；//true  ‘==’ 会自动转换数据类型再比较，结果诡异          
* false === 0；//false ‘===’不会进行数据类型转换，如果数据类型不一致返回‘false’，如一致再进行比较    
* <b>JS设计缺陷，不要使用==比较，始终坚持使用===比较 --廖雪峰</b>      
* <b>NaN</b>:   NaN === NaN;//false 与包括它自己的任何值都不相等，通过isNaN(NaN)；//true     
* <b>浮点数</b>:比较两个浮点数只能计算之差的绝对值是否小于某阈值：Math.abs(1/3-(1-2/3))<0.000001;//true    

null和undefined：null表示一个空的值，undefined表示值未定义。

数组：JS 的数组可以突破天际，包含任意数据类型（类似Java 实现collection的类？）
* 使用[]表示，元素之间用“，”分隔；    
* 使用Array()函数，new Array(1,2,3);//[1,2,3]
* JS 数组不存在outofbounds 问题，但是不推荐越界赋值    
* <url>https://www.liaoxuefeng.com/wiki/001434446689867b27157e896e74d51a89c25cc8b43bdb3000/00143449921138898cdeb7fc2214dc08c6c67827758cd2f000</url>

对象：JS的对象是一组由键值组成的无序集合(Java对象是某一类抽象事物的一个具体实例）；
<pre><code>
var person = {
    name:'Bob',
    age:20;
    tags:['js','web','mobile'],
    city:'Beijing',
    hasCar:true,
    zipcode:null
};
</code></pre>
    JS对象的键都是字符串类型（爱称对象的属性），值是任意类型；通过‘preson.name’ 获取对象的属性值
 
变量：var 声明一个变量，使用‘=’对变量赋值，类型可变（java 一旦声明变量类型，只能接受该类型的值）

strict模式：
* 启用strict模式在JS代码的第一行写上'use strict';
* JS使用未用var 声明的变量，该变量被标记为全局变量，同一个页面的不同js文件中的同名变量未使用var声明，造成混淆    
* 启用strict模式，未使用var声明的变量在使用时，将导致运行错误      
* 不支持strict模式的浏览器当作字符串语句执行，支持strict模式的浏览器开启strict模式



