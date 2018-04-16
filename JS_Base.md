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
          模板字符串  var message= 'Hello!' + name + ',you are ' + age +'years old!';    
          ES6        var message = 'Hello!${name},you are ${age} years old!';
          
布尔值：布尔值和布尔代数表示完全一致，只有（true 和 false）     

比较运算符：JS允许对任意数据类型做比较       
           false == 0；//true  ‘==’ 会自动转换数据类型再比较，结果诡异        
           false === 0；//false ‘===’不会进行数据类型转换，如果数据类型不一致返回‘false’，如一致再进行比较    
           <b>JS设计缺陷，不要使用==比较，始终坚持使用===比较 --廖雪峰</b>      
           <b>NaN</b>:   NaN === NaN;//false 与包括它自己的任何值都不相等，通过isNaN(NaN)；//true     
           <b>浮点数</b>:比较两个浮点数只能计算之差的绝对值是否小于某阈值：Math.abs(1/3-(1-2/3))<0.000001;//true    

null和undefined：null表示一个空的值，undefined表示值未定义。

数组：JS 的数组可以突破天际，包含任意数据类型（类似Java 实现collection的类？）
            使用[]表示，元素之间用“，”分隔；    
            使用Array()函数，new Array(1,2,3);//[1,2,3]
