# 第0篇 怪异模式，标准模式，严格模式

## 怪异模式

​	 早期的 `netscape4` 和 `ie4`，在实现 css 机制的时候，并没有遵循 w3c 的标准（主要是css实现盒模型的问题），为了保证自己的网站在不同的浏览器中都能正确展现，网页开发者不得不根据各个浏览器的自身的规范来使用css。而不同浏览器根据自己不同的实现去解析的这种行为，就称为怪异模式。

​	虽然这是早期的浏览器行为，但是浏览器厂商逐步实现w3c标准的同时，为了向下兼容，依然保留有怪异模式。（比如IE的怪异模型盒子）



## 标准模式

​	 根据w3c的标准来渲染和解析css机制，所有浏览器的渲染结果将一致。

​	

## 声明文档类型来控制怪异模式和标准模式

 只要声明了如下内容的文档声明，都会开启标准模式； 如果文档声明，或者文档声明错误，就会开启怪异模式。

 文档声明都是放在HTML文件的第一行位置。

1. html4.0.1文档类型声明

   ```html
   <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Strict//EN" 
   	"http://www.w3.org/TR/html4/strict.dtd">
   
   或者
   
   <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
   ```

   

2. xhtml4.0.1文档类型声明

   ```html
   <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
   
   或者
   <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
   
   或者
   <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">
   ```

   - XHTML  元素必须被正确的嵌套。

   - XHTML  元素必须被关闭。

   - 标签名必须用小写字母。

   - XHTML 文档必须拥有根元素。

     

3. h5文档类型声明

    ```html
<！DOCTYPE html>
    ```

​	 以后都用\<! DOCTYPE html>就行，具有良好的向下兼容性。	 





## 怪异模式和标准模式的区别

1. 盒模型

   ```html、
   怪异盒模型（IE盒模型）： 
      特点： width = content_width + border_left_width + border_right_width;
   		 height = content_height + border_top_width + border_bottom_width;
   
   标准盒子模型
   		width = content_width;
   		height = content_height;
   
   不需要使用怪异模式也可以使用怪异盒子模型，通过`box-sizing`可以控制
   		box-sizing: border-box; #开启怪异盒模型。
           box-sizing: content-box;#开启标准盒模型，默认值。
   ```

   

2. 图片元素的垂直对齐方式

   ```html
   标准模式下， inline 元素和 table-cell 元素，vertical-align属性默认取值为baseline.
   怪异模式下， inline 元素和 table-cell 元素，vertical-align属性默认取值为bottom.
   ```

   

3. \<table>元素中的字体

   ```html
   标准模式下，font的属性，都会通过继承传递给子元素。
   怪异模式下，对于table元素，字体的某些元素将不会从body等其他封装元素中继承得到，尤其是font-size。
   ```

   

4. 内联元素的尺寸

   ```html
   标准模式下，inline元素无法指定width，height;
   怪异模式下，可以指定inline元素的width，height;
   ```

5. 元素的百分比高度

   ```
   CSS中对于元素的百分比高度规定如下：百分比为元素包含块的高度，不可为负值，如果包含块的高度没有显示给出，该值等同于auto，所以百分比的高度必须在父元素有高度声明的情况下使用。当一个元素使用百分比高度时，标准模式下，高度取决于内容变化，怪异模式下，百分比高度被正确应用。
   ```

   

6. 元素溢出的处理

   ```html
   标准模式下，overflow取默认值visible，在怪异模式下，该溢出会被当做扩展box来对待，即元素的大小由其内容决定，溢出不会裁减，元素框自动调整，包含溢出内容。
   ```

   



## 严格模式

​	  JS1.8.5新增，对应ES5。 通过“use strict”字符串来开启一种更为严格的解析方式（主要针对js）。

  

1. 浏览器支持情况

   ```
   IE10+, Firefox4+, chrome 13+, safari5.1+, opera12+
   ```

2. 严格模式声明（开启） 

   ```js
   #严格模式通过在脚本文件或者函数中的头部添加 "use strict" 表达式来声明。
   #不支持严格模式的老版本浏览器会忽略掉该字符串。
   
   形式1：
     在js文件中，在文件行首声明严格模式。
     	#假设在test.js文件中
   	"use strict" 
   
   形式2：
      在js函数体内，在第一行声明严格模式。
   	function test(){
      		 "use strict"  #在函数体内声明严格模式，该声明只作用于函数体内。
   	}
   
   形式3：
   	在<script>标签中，在第一行声明严格模式。
   	<script>
       	"use strict"
       </script>
   
   ```

   3.严格模式出现的目的

   ```js
   1.消除javascript语法的不合理，不严谨之处，减少一些怪异行为。
   2.消除代码运行的不安全之处，保证代码运行的安全。
   3.提高编译器效率，增加运行速度。
   4.为未来新版本的javascript做好铺垫。
   ```

   4.声明严格模式之后的改变

   - 全局变量显示声明

     ```js
     #未声明严格模式的情形下运行
     #在非严格模式下运行，变量如果没哟声明就使用，则默认其声明成为window对象的属性。
     <script>
         a = 10;
         console.log(a); #10
         console.log(window.a); #10
     </script>
     
     #使用"use strict"启动严格模式
     <script>
         a = 10;  #直接报错，变量未定义。
     	console.log(a);
     	console.log(window.a)
     </script>
     ```

     

   -   禁止使用 with 语句。

     ```
     #1.什么是with
     	with语句为逐级的对象访问提供命名空间式子的速写方式。也就是说在指定的代码区域，直接通过节点名称调用对象。with通常被当做重复引用同一个对象中的多个属性的快捷方式，可以不需要重复引用对象本身。
     	用法举例：
             var obj = {
                 name: "mengze",
                 gender: '男'
             }
             with(obj){
                 name = 'mengze111'，
                 gender = '女',
                 age = 18
             }
             console.log(obj)
     
     #2.with的缺点
     	（1）在with中赋值的属性，如果该属性没有关联到with(obj)的obj上，则会直接泄露到全局对象中。
     		具体原因可以百度 `LHS查询`.
     	        var age;
                 console.log(age);
                 var obj = {
                     name: 'mengze',
                     gender: '男'
                 }
                 with( obj ){
                     name = '孟泽111',
                     gender = '女',
                     age= 30
                 }
                 console.log(obj);
                 console.log(age);
                 
          （2）性能下降。  
          	  JavaScript 引擎会在编译阶段进行数项的性能优化。其中有些优化依赖于能够根据代码的词法进行静态分析，并预先确定所有变量和函数的定义位置，才能在执行过程中快速找到标识符。但如果引擎在代码中发现了 with，它只能简单地假设关于标识符位置的判断都是无效的，因为无法知道传递给 with 用来创建新词法作用域的对象的内容到底是什么。最悲观的情况是如果出现了 with ，所有的优化都可能是无意义的。因此引擎会采取最简单的做法就是完全不做任何优化。如果代码大量使用 with 或者 eval()，那么运行起来一定会变得非常慢。无论引擎多聪明，试图将这些悲观情况的副作用限制在最小范围内，也无法避免如果没有这些优化，代码会运行得更慢的事实。
     
     
     #3.严格模式遇到with就直接报错 Strict mode code may not include a with statement。
     	"use strict"
     	var obj = {
     		name: "mengze",
     		gender: '男'
     	}
     	with(obj){
     		name = 'mengze111'，
     		gender = '女',
     		age = 18
     	}
     	console.log(obj)
     ```

     

   -   设置 eval 作用域。  

     ```html
     正常模式下， js语言有两种作用域（ES6以前）： 全局作用域和函数作用域。严格模式创设了第三种作用域：eval作用域。
     ```

     

   - 禁止this关键字指向全局对象window。

   - 禁止在函数内部遍历调用栈。

   - 禁止删除变量

   - 显示报错

   - 重命名错误

   - 函数不能有重名的参数

   - 禁止八进制表示法

   - arguments对象的限制

   - 函数必须声明在顶层，或者函数体内

   - 保留字

     

     

# 第一篇 标识符，变量，常量，关键字，数据类型，判断数据类型

# 第二篇 运算符，条件判断，类型转换

# 第三篇 条件判断， 循环，continue， break

# 第四篇  字符串与正则表达式

# 第五篇 函数，闭包

# 第六篇 Object

# 第七篇 数组，set，map，链表，队列，栈， LRU实现

# 第八篇 定义类，原型链

# 第九篇  继承

# 第十篇 多态

# 第十一篇 网络

# 第十二篇 promise，微队列，宏队列