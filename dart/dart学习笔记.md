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

  ```dart
    //常量方式定义Map对象。
    Map person = {
      "name": "张三",
      "age": 24,
      "work": ["程序猿", "送外卖"]
    };
  
    var person2 = {
      "name": "李四",
      "age": 25,
      "work": ["工程师", "滴滴司机"]
    };
  
    //new方式定义Map对象。
    Map person3 = new Map();
    //Map对象增加key-value的形式，如果key相同，则覆盖原来的值
    person3["name"] = "王五";
    person3["age"] = 26;
    person3["work"] = ["护士", "主任"];
  
    print(person);
    print(person2);
    //Map对象获取值的方式 （注意，dart中不能用.点方式获取key-value）
    print(person3["work"]);
  ```

  

  

- runes

- symbol

  

## 判断数据类型（is关键字）

```dart
# is关键字用于判断变量是否属于某个类型，其中int，double，bool，list在dart中都是对象类型。  
int a = 10;
String hello = "world";
List list = ["a", "b", "c"]; 
bool isInt = a is int;  //是不是int类型
bool isString = hello is String; //是不是字符串类型
bool isArray = list is List;  //是不是数组类型
print(isInt);
print(isString);
print(isArray);
```



## Number类型变量的常见属性和方法

```dart
int a = 10;
double b = 20.12;

//int类型常见属性
//a.isNegative; 是否是负数
//a.isFinite;   是否是正无穷或者负无穷
//a.sign;       -1.0 表示是负数; 1.0表示是正数; 0则表示不正不负;
//a.hashCode;   hash编码
//a.isOdd;      是否是奇数
//a.isEven;     是否是偶数
//a.bitLength;  字节长度 4
//a.isNaN;      是否非num类型数据

//int类型常见方法
//1. 获取绝对值   a.abs()
//2. int转字符串  a.toString()
//3. 转指定进制的字符串 a.toRadixString(2|8|16)
//4. 转double类型数据 a.toDouble()
//5. 字符串转int类型  int.parse('123') #如果是12.3或者12a3则报错。


=============================================>
//double类型常见属性
//b.isNegative; 是否是负数
//b.isFinite; 是否是无穷数
//b.sign;   获取符号
//b.isNaN;  是否非num类型数据

    
// double类型常见方法
//1.截断取整  b.toInt()
//2.转字符串  b.toString()
```

## bool类型的常用方法

```dart
  bool test = true;
  print(test.toString());
```



## String类型变量的常用方法

```dart
暂时省略不写，一门语言中， string，list，map方法是做多的。

```



# 第四篇 运算符，条件判断，类型转换

## 算术运算符

```dart
#注意：dart中两个整数相除，无论是否除尽，都是返回double类型数据。
#     dart中能对正整数，正浮点数取模，但是不能对负数取模。 a.sign * (a.abs() % 3)
    
+ 加； - 减； * 乘； / 除 ； ~/ 除且结果取整； % 取模；
int a = 10;
int b = 2;
int result1 = a + b;
int result2 = a - b;
int result3 = a * b;
double result4 = a / b;
// int result4 = 10 / 2; // dart中两个整数相除，无论是否除尽，都是返回double类型数据。
int result5 = a ~/ b; //除，且结果去整。
print(result1); //12
print(result2); //8
print(result3); //20
print(result4); //5.0
print(result5); // 5

#关于对负数取模的处理
int result = a.sign * (a.abs() % 3)
```



## 关系运算符

```dart
# 关系运算符的表达式结果是bool类型。
==等于, !=不等于, > 大于, <小于, >=大于等于， <=小于等于

#dart中没有js中的===，!==; 
# 1.因为dart在进行相等，不等操作的时候，对于类型不同的数据，不会进行数据类型转换（除了int，double类型的隐式转换）。
# 2.虽然dart不进行隐式的类型转换，但是允许不同类型的数据进行比较。
    
  int a = 10;
  double b = 20;
  String c = "hello";
  bool result = a == b;
  bool result2 = a != b;
  bool result3 = a > b;
  bool result4 = a >= b;
  bool result5 = a < b;
  bool result6 = a <= b;

  print(result);
  print(result2);
  print(result3);
  print(result4);
  print(result5);
  print(result6);

  bool res = a == c;
  bool res2 = a != c;
  print(res);
  print(res2);

  Map map = {"name": "meng"};
  print("----------------------");
  print(map != a);
    
```



## 逻辑运算符

```dart
# 逻辑运算符表达式的结果是bool类型; 且逻辑运算符的操作数只接受bool类型的值。
!取反， && 逻辑与， || 逻辑或

int a = 3;
int b = 20;

// 1. 逻辑运算符的左右两边的操作数都必须是bool类型。
// bool c = !a; //报错
// bool c = a || b; //报错
// bool c = a && b; //报错

// 2. 逻辑或 || , 逻辑与 && 具有短路原则特性。
//    即： 当||的左边操作数或者表达式已经确定是true的情况下，不再执行右边。
//        当&&的左边操作数或者表达式已经确定是false的情况下，不再执行右边。
if (a == 3 || ++a == 4) {
    print(a);
}

// 3. dart中&&， || 与 js中的&&， ||
//    相同点：都具有短路原则特性。
//    不同点：dart中的逻辑运算符的操作数只能是bool类型，且返回结果也是bool类型。而js中的逻辑云算法的操作可以是任意类型，且返回结果是已执行表达式的最后部分的值。比如js中常用的表达式:  let a = temp || {};  a && test();
```



## 赋值运算符，复合赋值运算符

```dart
int a = 0;
int b = 20;
a = b; //赋值运算.

a += 10;
a -= 10;
a *= 20;
// a /= 10;  复合运算符中不包含强制类型转换，所以表达式的结果与要复制的变量类型不一致，那么编译器报错。
a ~/= 10;
```



## ++, --

```dart
前++， 后++， 前--， 后--

# 1. 前++， 前-- 
#   在表达式中对含有前++，--的变量进行增减1操作，然后再进行表达式运算。
int a = 10;
if (++a == 10 && a == 11) {
    print("true: " + a.toString());
} else {
    print("fasle: " + a.toString());
}  #输出结果为： false: 11

    
# 2. 后++, 后--
#    在表达式中对含有后++，--的变量先进行临时变量备份，再进行该变量的增减-操作，然后再进行表达式运算，其中含有++，--的该变量，被临时变量的值所替代。
int a = 10;
if (a++ == 10 && a == 11) {
    print("true: " + a.toString());
} else {
    print("fasle: " + a.toString());
}  #输出结果为： true:11
```



## ?? 与 ??=

```dart
# a ?? b （如果a表达式或者函数为bull，那么执行b表达式或者函数。）
# c = a ?? b;
# a ??= b;  就是 a = a ?? b; (如果a为null，那么久执行b表达式或者函数)
    
int a = null;
int b = a ?? 10; //如果a为null，则b==10
print(b);
if (a != null) {
    b = a;
} else {
    b = 10;
}

a = null;
a ??= 10; //如果a为bull，那么a=10;否则不赋值。
print("a: ${a}");
if (a == null) {
    a = 10;
}

========================================>
int test1() {
    print(123);
    return null;
}

int test2() {
  print(234);
  return 2;
}
test1() ?? test2();

#总体而言，??, ??= 就类似于js中的&&; 减少了一个if判断语句而已。
```



- 三目运算符

  ```dart
  # a = b ? c : d
  ```



# 第五篇 条件判断，循环，continue，break

## if, if...else, if...else if...else

```dart
//dart是强类型语言，if表达式中只接受bool类型的值或者表达式
//像 int a = 0; if( a ) { print(a) } 这个表达式会报错处理。

int a = 20;
//1. if
if (a > 20) {
    print(a);
}

//2. if..else
bool b = true;
if (b) {
    print("真");
} else {
    print("假");
}

//3. if...else if...else
int c = 60;
if (c > 80) {
    print("80分以上");
} else if (c > 60) {
    print("60~80分之间");
} else {
    print("60分以下");
}
```



## switch , case, default

```dart
/**
   * 1. dart中case右边的参数必须是常量， 且类型必须一致。
   * 2. dart中case需要break结尾，否则出现贯穿现象。
  */
String language = "Dart";
switch (language) {
    case "Javascript":
        print("Javascript");
        break;
    case "Dart":
        //贯穿效果演示
    case "Java":
        print("Java");
        break;
    default:
        break;
}
```

## for, for in, while, do...while

```dart
void main() {
  List list = ["apple", "pear", "banana", "lemon"];
  Map map = {"name": "meng", "age": "30", "gender": "male"};
  for (int i = 0; i < list.length; i++) {
    print(list[i]);
  }

  // 1. dart中的for...in 循环 与 js中的不同； dart中的for...in 直接获取到的是value值，而不是索引。
  for (String item in list) {
    print(item);
  }
  for (String index in map.keys) {
    print("index: $index, item: ${map[index]}");
  }

  /**
   * 明确知道循环次数的循环，使用for，for in 会更方便。
   * while则一般用于不知道循环次数，需要根据某个条件来判断结束的情况。
   */
  int i = 0;
  while (true) {
    if (i > 10) {
      break;
    }
    print(i);
    i++;
  }

  // 挺少用到
  // 特点是： 先执行一次循环体，然后再判断条件是否继续执行
  do {
    print(i);
    i++;
  } while (i < 10);
}

```





## continue, break

```dart
# continue : 用于结束本次循环，开始下一次循环；主要作用就是循环体内continue后的语句不需要再执行。
# break： 跳出内层循环，该层循环结束；主要作用就是本次循环结束，不用在执行。

    for (int i = 0; i < 10; i++) {
        for (int j = 0; j < 10; j++) {
            if (j < 5) {
                continue;  # 用于结束本次循环。
            }
            print("i: $i, j: $j");
            if (i > 8) {
                break; # 用于结束本轮循环。
            }
        }
    }
```





# 第六篇 list, set, map详解，forEach, map, where, any, every

```dart

```



# 第七篇 函数定义与形参，箭头函数，匿名函数，闭包

# 第八篇 类与对象

# 第九篇 类， 静态成员，操作符，继承

# 第十篇  抽象类，接口，多态

# 第十一篇 类实现多个接口，以及mixins

# 第十二篇 泛型，泛型方法，泛型类，泛型接口

# 第十三篇 库，自定义库，系统库，第三方库







```dart
void main() {
  /***
   * 1.关于const 修饰 List
   *    (1) 被const修饰的List，初始化的时候只允许使用常量形式的数组初始化, 且常量形式数组中的元素也不能含有变量， 不能用new List()方式。
   *    (2) 被const修饰的List，不允许增加，删除，修改元素； 且不能被其他变量引用的数组所初始化;
   *   所以dart中的const 与 js中的const不同，dart中的const只建议用在int,double, string上；
   *    
   *    //正确情形
   *    const list = ["Java", "Js"]
   *    const list1 = [{ "language": "java"; "salary": "20000" }, {"language": "js"; "salary": "10000"}]
   *     
   *    //错误情形:
   *    
   * 
   * 2.关于final 修饰 List
   *    dart中的final相当于js中的const，被修饰的变量不允许再被直接赋值，但是如果是对象或者数组，则允许修改内部属性或者元素；
   */

  //1.初始化
  //  对List类型变量使用const关键字限定，数组将会变为 unmodifiable list， 即不可以直接增加，修改，删除元素。

  const temp = "123";
  final list = ["Java", temp, "object-c", "dart"];
  list[2] = "";
  print(list);
  var list1 = new List();
  list1.add(["Java", "Javascript", "object-c", "dart"]);

  var map = {"name": 'meng', "age": 18};

  final list2 = [map];
  list2[0] = {"name": 'meng', "age": 19};
  list2.add({"name": 'meng', "age": 20});

  list[1] = "c++";
  /**
   * List的常用属性
   *  length: 获取数组的长度
   */
  int length = list.length;

  List a = null;
  /***
   * List的常用方法
   * 1. 增加单个元素到数组末尾
   * 2. 增加多个元素到数组末尾(以数组形式传参)
   * 3. 判断数组是否为空
   * 4. 判断数组是否不为空
   */
  // list.add("pyhton");
  // list.addAll(["golang", "kotlin", "c", "c++"]);

  // print(a.runtimeType);
}

void test(final List list) {}

```





