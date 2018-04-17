JS_Base2

变量作用域和解构赋值：
* 同Java变量作用域    
* 变量提升，先扫描整体函数体，把所有声明的变量提升到函数顶部，赋值仍然按语句顺序
<pre><code>
    function foo() {
        var x = 'Hello, ' + y;
        console.log(x);
        var y = 'Bob';
    }

    foo();
    
    //相当于：
    function foo() {
        var y; // 提升变量y的申明，此时y为undefined
        var x = 'Hello, ' + y;
        console.log(x);
        y = 'Bob';
    }
</code></pre>
* 所以在函数内部定义变量时，遵循：在函数内部首先声明所有变量

全局变量：
* 不在任何函数内定义的变量具有全局作用域　　　　
* JS默认有一个全局对象window，全局作用域的变量实际上是被绑定到window的一个属性    

命名空间：
* 全局变量绑定到window 上，不同的js文件如果使用相同的全局变量，或者定义了相同名字的顶层函数，造成命名冲突    
* 减少冲突的一个方法就是将自己的变量和函数绑定到一个全局变量中
