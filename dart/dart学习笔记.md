[toc]



# 第一篇 dart2简介

## dart的主要用途

* `移动端开发`：配合flutter，为 IOS 和 Android 制作高质量的原生界面。

* `web开发`:  dart经过关键性web应用程序验证的平台。拥有为web量身打造的库，如dart:html, 以及完整的基于dart的web框架。

* `服务端开发`

​	 

## dart2安装

​		参考博客：  https://blog.csdn.net/qq_27494201/article/details/103230066 

 

## 第一个dart程序 hello dart

```dart
void main(){
    print("hello dart");
}
```





# 第二篇 入口方法，变量，常量，标识符

## 入口方法

```dart
#因为dart语言的函数，可以不写参数类型、返回值类型，所以入口方法main可以写成两种形式
main(){
    print("hello dart")
}

#或者
void main(){
    print("hello dart")
}
```



## 声明变量

```dart
#dart是强类型语言，即每个对象都必须有类型，且类型在运行时不允许更改。
#但是dart也支持类型推导，当使用var关键字声明变量时，将从等号右边的表达式结果推导出左边变量的类型。

int a = 12;
String hello = "hello world!";
// var workd = a + hello;  # dart中的+号，虽然也有连字符的作用，但是不能用于"基础类型+字符串类型"。
var world = a.toString() + hello; // var声明的变量，会通过右边的表达式推导出类型。
```





## 声明常量

```dart
#dart中声明常量有两种关键字， final和const关键字， 经测试：final，const都需要在声明的时候就需要初始化，否则编译直接报错.

  const int a = 10;
  final String hello = "world";
  const b = 20;
  final c = 30;
  //当定义常量，且需要类型推导时，不需要var关键字。而是直接使用const， final即可。
  //const var e = 20;
  //final var d = 30;
  print(a);
  print(b);
  print(c);
  print(hello);
```



## 标识符命名规则

- 凡是数据类型，类名，方法名，变量名，常量名，对象名等，都是标识符。
- 标识符必须由数字，字母，下划线(_),  美元符号($) 组成，但是不建议以$开头。
- 标识符不能以数字开头。（避免与0F, 1L等数据混淆）
- 标识符不能是dart语言的关键字和保留字。
- 标识符严格区分大小写（比如username与userName是两个的标识符）。
- 标识符命名最好能见名知义，禁止使用拼音； 变量名建议用名词，方法名建议用动词。

## 关键字

| 关键字        | 关键字含义 |
| ------------- | ---------- |
| abstract(2)   |            |
| dynamic(2)    |            |
| implements(2) |            |
| show(1)       |            |
| as(2)         |            |
| esle          |            |
| import(2)     |            |
| static(2)     |            |
| assert        |            |
| enum          |            |
| in            |            |
| super         |            |
| async(1)      |            |
| export(2)     |            |
| interface(2)  |            |
| switch        |            |
| await(3)      |            |
| extends       |            |
| is            |            |
| sync(1)       |            |
| break         |            |
| external(2)   |            |
| library(2)    |            |
| this          |            |
| case          |            |
| factory(2)    |            |
| mixin(2)      |            |
| throw         |            |
| catch         |            |
| false         |            |
| new           |            |
| true          |            |
| class         |            |
| final         |            |
| null          |            |
| try           |            |
| const         |            |
| finally       |            |
| on(1)         |            |
| typedef(2)    |            |
| continue      |            |
| for           |            |
| operator(2)   |            |
| var           |            |
| covariant(2)  |            |
| Function(2)   |            |
| part(2)       |            |
| void          |            |
| default       |            |
| get(2)        |            |
| rethrow       |            |
| while         |            |
| deferred(2)   |            |
| hide(1)       |            |
| return        |            |
| with          |            |
| do            |            |
| if            |            |
| set(2)        |            |
| yield(3)      |            |

避免使用这些单词作为标识符。但是，如有必要，标有上标的关键字可以是标识符：

- 带有（1）的单词是上下文关键字，仅在特殊位置上有意义。它们在任何地方都是有效的标识符。
- 带有（2）的单词是内置标识符。为了简化将javascript代码移植到Dart, 这些关键字在大多数地方都是有效的标识符，但它们不能作为类或者类型名称，也不能用于导入前缀。
- 带有（3）的单词是与dart1.0发布后添加的<font color='red'>异步支持</font>相关的有限保留字。不能在任何被标记 <font color='red'>`async`, `async*`</font>或者<font color='red'>`sync*`</font>标记的函数体重使用<font color='red'>`await`</font>或者<font color='red'>`yield`</font>作为标识符。



# 第三篇 数据类型, 判断数据类型

## dart中的数据类型

 首先：dart中所有类型（包括基础类型），都是类。也就是说一切皆对象。

- numbers (数字类型具体的类型是 int，double)

  - int， double都继承自抽象类num。

  - 整数的number类型 int， 32位或者64位，取决于dart虚拟机。（注意这里没有samll int, byte, long等其他语言的整型类型）。  
  - 浮点数的number类型 double， 64位 （注意这里没有其他语言的float类型）。    

  ```dart
  #int,double都是对象类型，继承自num类型。
  #其中 int 根据dart虚拟机的位数，分为 32 位或者 64 位长度。
  #其中 double 为 64 位长度。
  #定义 int, double 类型的变量的形式。
  int a = 10;
  double b = 20.0;
  var a = 10;
  var b = 20.0;
  
  #定义int，double类型的常量的形式。
  const a = 10;
  final a = 10;
  const b = 20.0;
  final b = 20.0;
  ```

- String  字符串类型

  ```dart
  #定义String类型的变量的形式。
  String hello = "world";
  var hello = "world";
  
  #定义String类型的常量的形式。
  const hello = "world";
  final hello = "world";
  ```

  

- bool 布尔类型

  ```dart
  #bool类型定义的关键字为 bool, 其中只有两个内置的常量值： true, false
  bool a = true;
  bool b = false;
  var  a = true;
  var  b = false;
  ```

  

- list 数据或者列表

  ```dart
  #常变量形式定义List类型的对象。
  List list = ['a', 'b', 'c'];
  
  #采用new的方式定义List类型的对象，且使用addAll()方式进行初始化。
  List list1 = new List();
  list1.addAll(['a', 'b', 'c']);
  
  print(list);
  print(list1);
  ```

  

- map 字典

- runes

- symbol

## 判断数据类型（is关键字）

```dart
# is关键字用于判断变量是否属于某个类型，其中int，double，bool，list在dart中都是对象类型。  
int a = 10;
String hello = "world";
List list = ["a", "b", "c"];
bool isInt = a is int;
bool isString = hello is String;
bool isArray = list is List;
print(isInt);
print(isString);
print(isArray);
```



## Number类型变量的常用方法

## String类型变量的常用方法

# 第四篇 运算符，条件判断，类型转换

# 第五篇 循环，continue，break

# 第六篇 list, set, map详解，forEach, map, where, any, every

# 第七篇 函数定义与形参，箭头函数，匿名函数，闭包

# 第八篇 类与对象

# 第九篇 类， 静态成员，操作符，继承

# 第十篇  抽象类，接口，多态

# 第十一篇 类实现多个接口，以及mixins

# 第十二篇 泛型，泛型方法，泛型类，泛型接口

# 第十三篇 库，自定义库，系统库，第三方库







