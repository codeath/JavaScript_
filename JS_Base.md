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
数组常用方法：    
* indexOf();//指定元素的位置
* slice()就是对应String的substring()版本，它截取Array的部分元素，然后返回一个新的Array：
<pre><code>
var arr = ['A', 'B', 'C', 'D', 'E', 'F', 'G'];
arr.slice(0, 3); // 从索引0开始，到索引3结束，但不包括索引3: ['A', 'B', 'C']
arr.slice(3); // 从索引3开始到结束: ['D', 'E', 'F', 'G']
</code><pre>
注意到slice()的起止参数包括开始索引，不包括结束索引。
如果不给slice()传递任何参数，它就会从头到尾截取所有元素。利用这一点，我们可以很容易地复制一个Array：
<pre><code>
var arr = ['A', 'B', 'C', 'D', 'E', 'F', 'G'];
var aCopy = arr.slice();
aCopy; // ['A', 'B', 'C', 'D', 'E', 'F', 'G']
aCopy === arr; // false
</code></pre>
* push和pop: push()向Array的末尾添加若干元素，pop()则把Array的最后一个元素删除掉： 
<pre><code>
var arr = [1, 2];
arr.push('A', 'B'); // 返回Array新的长度: 4
arr; // [1, 2, 'A', 'B']
arr.pop(); // pop()返回'B'
arr; // [1, 2, 'A']
arr.pop(); arr.pop(); arr.pop(); // 连续pop 3次
arr; // []
arr.pop(); // 空数组继续pop不会报错，而是返回undefined
arr; // []
</code></pre>
* unshift和shift: 如果要往Array的头部添加若干元素，使用unshift()方法，shift()方法则把Array的第一个元素删掉：
<pre><code>
var arr = [1, 2];
arr.unshift('A', 'B'); // 返回Array新的长度: 4
arr; // ['A', 'B', 1, 2]
arr.shift(); // 'A'
arr; // ['B', 1, 2]
arr.shift(); arr.shift(); arr.shift(); // 连续shift 3次
arr; // []
arr.shift(); // 空数组继续shift不会报错，而是返回undefined
arr; // []
</code></pre>
* sort: sort()可以对当前Array进行排序，它会直接修改当前Array的元素位置，直接调用时，按照默认顺序排序：
<pre><code>
var arr = ['B', 'C', 'A'];
arr.sort();
arr; // ['A', 'B', 'C']
</code></pre>
* reverse:reverse()把整个Array的元素给掉个个，也就是反转：
<pre><code>
var arr = ['one', 'two', 'three'];
arr.reverse(); 
arr; // ['three', 'two', 'one']
</code></pre>
* splice:splice()方法是修改Array的“万能方法”，它可以从指定的索引开始删除若干元素，然后再从该位置添加若干元素：
<pre><code>
var arr = ['Microsoft', 'Apple', 'Yahoo', 'AOL', 'Excite', 'Oracle'];
// 从索引2开始删除3个元素,然后再添加两个元素:
arr.splice(2, 3, 'Google', 'Facebook'); // 返回删除的元素 ['Yahoo', 'AOL', 'Excite']
arr; // ['Microsoft', 'Apple', 'Google', 'Facebook', 'Oracle']
// 只删除,不添加:
arr.splice(2, 2); // ['Google', 'Facebook']
arr; // ['Microsoft', 'Apple', 'Oracle']
// 只添加,不删除:
arr.splice(2, 0, 'Google', 'Facebook'); // 返回[],因为没有删除任何元素
arr; // ['Microsoft', 'Apple', 'Google', 'Facebook', 'Oracle']
</code></pre>
* concat:concat()方法把当前的Array和另一个Array连接起来，并返回一个新的Array：
<pre><code>
var arr = ['A', 'B', 'C'];
var added = arr.concat([1, 2, 3]);
added; // ['A', 'B', 'C', 1, 2, 3]
arr; // ['A', 'B', 'C']
</code></pre>
请注意，concat()方法并没有修改当前Array，而是返回了一个新的Array。
实际上，concat()方法可以接收任意个元素和Array，并且自动把Array拆开，然后全部添加到新的Array里：
<pre><code>
var arr = ['A', 'B', 'C'];
arr.concat(1, 2, [3, 4]); // ['A', 'B', 'C', 1, 2, 3, 4]
</code></pre>
* join:join()方法是一个非常实用的方法，它把当前Array的每个元素都用指定的字符串连接起来，然后返回连接后的字符串：
<pre><code>
var arr = ['A', 'B', 'C', 1, 2, 3];
arr.join('-'); // 'A-B-C-1-2-3'
</code></pre>
如果Array的元素不是字符串，将自动转换为字符串后再连接。



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



