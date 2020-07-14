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

## List

​	List的下标index，从0开始。

### List初始化

```dart
#1.创建并且初始化数组List
# 常量数组形式创建并且初始化数组。
List<String> list1 = ["Java", "Javascript", "object-c", "dart"];
# 当然，常量形式的数组，内部元素可以是变量。
const temp = "123";
List<String> list2 = ["Java", "Javascript", "object-c", "dart", temp];
# 使用new方式创建数组，可以指定数组的初始长度。可以通过addAll()添加多个元素。
var list3 = new List();
list1.add(["Java", "Javascript", "object-c", "dart"]);
```



### List常用属性

| 常用属性   | 说明                                                         |
| ---------- | ------------------------------------------------------------ |
| length     | 获取List的长度。                                             |
| reversed   | 获取数组的逆向集合，返回一个Iterable对象。可以通过iterable.toList()转成List。 |
| isEmpty    | List的长度是否为0。                                          |
| isNotEmpty | List的长度是否不为0。                                        |
| first      | List中的第一个元素值。                                       |
| last       | List中的最后一个元素值。                                     |
| iterator   | List的遍历器对象。                                           |

```dart
  /**
   * 1.常见属性
   *    length: 获取数组的长度
   *    reversed： 获取一个逆序的集合。是一个ReversedListIterable对象。
   *    isEmpty:   判断数组是不是为空。
   *    isNotEmpty: 判断数组是否不为空。
   */

  //获取数组的长度
  var length = list1.length;
  print("length: $length");

  //获取数组的逆序列表，不直接是一个List对象，而是一个ReveredListIterable对象、
  Iterable iterable = list1.reversed;
  print(iterable.runtimeType);
  Iterator iterator = iterable.iterator;
  while (iterator.moveNext()) {
    print("item: ${iterator.current}");
  }
  //iterable对象转数组。
  List<String> reversed = iterable.toList();
  print(reversed);

  //是否为空
  bool isEmpty = list1.isEmpty;
  print("isEmpty: $isEmpty");

  //是否不为空
  bool isNotEmpty = list1.isNotEmpty;
  print("isNotEmpty: $isNotEmpty");

  //获取遍历器对象
  Iterator iterator = list1.iterator;
 //获取第一个元素
  String first = list1.first;
  //获取最后一个元素
  String last = list1.last;
	
  print(list1);
  print("iterator: $iterator");
  print("last: $last");
  print("first: $first");
  print(list1);
```



### List常用方法

```dart
  /**
   *  增加
   *  list.add( e );
   *  list.addAll( iterable )
   *  list.insert( index, e )
   *  list.insertAll( index, iterable )
   */
  //增加  list.add();  list.addAll()
  list1.add("c"); //在数组末尾增加单个元素。
  list1.addAll(["c++", "go", "perl"]); //在数组末尾增加多个元素
  print(list1);

  list1.insert(1, "vb"); //在指定index下插入元素。注意：index从0开始。
  print(list1);

  //set, list, Map.getKeys() 都是iterable对象
  list1.insertAll(0, list1.reversed); //第二个参数只需要是Iterable对象即可.
  print(list1);



/**
   List 删除元素
   * 删除
   * 1. list.removeLast()
   * 2. list.removeAt( index ) 删除指定index的List中的元素
   * 3. list.remove( element ) 删除指定element的List中的元素, 且只删除第一个遇到的元素。
   * 4. list.removeWhere( (value){ } ) 遍历数组，判断数组元素是否需要删除，如果删除返回true，否则返回false。
   * 5. list.removeRange( 2, 3) //删除一个数组的子集，第一个参数是startIndex，第二个参数是endIndex（注意不是length）。删除范围包含start，不包含end。
*/
  print(list1);
  list1.removeLast(); //删除List最后一个元素、
  print("===========================  removeLast");
  print(list1);

  list1.removeAt(list1.length - 1); //
  list1.removeAt(0);
  print(list1);

  list1.remove("Java");
  list1.removeWhere((element) {
    return element == 'object-c';
  });
  print(list1);

  list1.removeRange(2,
      3); //删除一个数组的子集，第一个参数是startIndex，第二个参数是endIndex（注意不是length）。删除范围包含start，不包含end。
  print(list1);



/**
	List 修改元素
	1. 通过list[index] = xxx 形式进行修改。
	2. 批量重置  list.fillRange(0, list.length, "1");
	3. 批量修改  list.setRange( startIndex, endIndex, iterable<E> iterable, [int skipCount = 0] )
*/
List list = list1;
//通过 list[index] 方式修改
list[2] = "3456";

//批量重置
list.fillRange(0, list.length, "1");
print("fill list: $list");

//批量替换, 替换指定位置的元素。 替换list 与 被替换list 的 index 一一对应
//通过 list.setRange( startIndex, endIndex, iterable<E> iterable, [int skipCount = 0] )
list.setRange(1, 3, ["java", "swift", "dart", "eee"] as List<String>);
print("setRange: $list");

//删除指定范围，并用新的数组插入
list.replaceRange(1, 3, ["1", "2", "3", "4", "5", "6"] as List<String>);
print("replaceRange: $list");


/**
	List 查询元素
*/



/**
	List 其它方法
*/
```



### list.dart API文件翻译

```dart
#list.dart API文件翻译
part of dart.core;

/**
 * 一个可索引，有长度的的对象集合。
 * An indexable collection of objects with a length.
 *
 * 这个类的子类实现不同种类的list。
 * Subclasses of this class implement different kinds of lists.
 * 最常用的list种类有：
 * The most common kinds of lists are:
 *   （1）固定长度的list。 如果尝试去操作改变list的长度，那么就会报错。 
 * * Fixed-length list.
 *   An error occurs when attempting to use operations
 *   that can change the length of the list.
 *    
 *   （2）可增长的list， 这个API的全部实现都在这个类中。
 * * Growable list. Full implementation of the API defined in this class.
 *
 *   通过'[]'方式创建一个默认的可增长的list， 持有一个内部的buffer，并且这个buffer在必要的时候
 * 会增长。这个由增加操作组成的序列，每一次执行均摊常量时间。直接设置长度可能花费成正比的时间用于变更成新长度，
 * 并且为了接下来的增加操作需要立刻增加 buffer的容量而可能改变内部的容量。
 *   其它列表实现可能有不同的表现行为。
 * The default growable list, as created by `[]`, keeps
 * an internal buffer, and grows that buffer when necessary. This guarantees
 * that a sequence of [add] operations will each execute in amortized constant
 * time. Setting the length directly may take time proportional to the new
 * length, and may change the internal capacity so that a following add
 * operation will need to immediately increase the buffer capacity.
 * Other list implementations may have different performance behavior.
 *
 * //接下来的代码说明一些列表实现支持， 仅仅是这个API的子集合。
 * The following code illustrates that some List implementations support
 * only a subset of the API.
 *
 *     List<int> fixedLengthList = new List(5);
 *     fixedLengthList.length = 0;  // Error
 *     fixedLengthList.add(499);    // Error
 *     fixedLengthList[0] = 87;
 *     List<int> growableList = [1, 2];
 *     growableList.length = 0;
 *     growableList.add(499);
 *     growableList[0] = 87;
 *
 * 
 * 列表是可迭代的。 迭代发生在索引顺序的值上。增删值值不影响循环，但是会改变有效的索引。
 * 换句话说，在循环步骤之间，改变列表的长度，会导致一个ConcurrentModificationError错误。
 * 这意味着仅可增长列表能抛出ConcurrentModificationError错误。如果长度临时性改变，并且在
 * 在继续下一次循环前修复，这个迭代器不能检测到这种行为。
 * Lists are [Iterable]. Iteration occurs over values in index order. Changing
 * the values does not affect iteration, but changing the valid
 * indices&mdash;that is, changing the list's length&mdash;between iteration
 * steps causes a [ConcurrentModificationError]. This means that only growable
 * lists can throw ConcurrentModificationError. If the length changes
 * temporarily and is restored before continuing the iteration, the iterator
 * does not detect it.
 *
 * 
 * 当数组中一个操作被执行时，总体俩说是不允许改变数组的长度。（增加或者删除元素）
 * 举个例子： 在一个forEach或者sort被唤起时: 当处于循环中，或者直接迭代它，或者
 * 贯穿正迭代一个Iterable对象时，改变list的长度，将会被list回退， 从而跳出循环。
 * It is generally not allowed to modify the list's length (adding or removing
 * elements) while an operation on the list is being performed,
 * for example during a call to [forEach] or [sort].
 * Changing the list's length while it is being iterated, either by iterating it
 * directly or through iterating an [Iterable] that is backed by the list, will
 * break the iteration.
 */
abstract class List<E> implements EfficientLengthIterable<E> {
  /**
    external factory List([int? length]);
  
   * 根据给予的长度创建一个List.
   * Creates a list of the given length.
   *
   * 如果元素的类型，不是一个可以赋值为null的变量类型，将会抛出一个exception.在这种情况中，
   * 其它的构造器，比如List.filled()必须被使用。 (List.filled默认就是整个数组所有元素全部赋值为null)
   * This constructor will throw an exception if [E] is not a nullable type.
   * In this case, another constructor such as [List.filled] must be used
   * instead.
   *
   * 如果长度被提供，那么被创建的List就是固定长度的；不允许改变list.length的长度,否则报错。
   * The created list is fixed-length if [length] is provided.
   *
   *     List fixedLengthList = new List(3);
   *     fixedLengthList.length;     // 3
   *     fixedLengthList.length = 1; // Error
   *
   * 
   * 如果创建List时， length没有指定，那么List的长度为0，且是可增长的。
   * （允许直接修改list.length属性，如果length变大，则新增元素初始化为null,如果length变小，
   * 则数组相当于被截断。）
   * The list has length 0 and is growable if [length] is omitted.
   *
   *     List growableList = [];
   *     growableList.length; // 0;
   *     growableList.length = 3;
   *
   * 
   * 创建一个可增长的List，并且给予长度，元素都是可以设置为null的类型。 在创建时，仅仅分配
   * 右边指定的长度。 （ ..表示级联赋值 ）
   * To create a growable list with a given length, for a nullable element type,
   * just assign the length right after creation:
   *
   *     List growableList = []..length = 500;
   *
   * 
   * 对于元素是不能赋值为null的类型，一种选择是如下：
   * For a non-nullable element type, an alternative is the following:
   *
   *     List<int> growableList = List<int>.filled(500, 0, growable: true);
   *
   * 如果提供length值， 那么这个List的length必须不能是负数或者null。
   * The [length] must not be negative or null, if it is provided.
   *
   * 如果这个元素不能nullable，那么长度必须大于0;
   * If the element type is not nullable, [length] must not be greater than
   * zero.
   *
   * 这个构造器不能被用于null-safe的代码。
   * 使用List.filled（）方法去创建一个非空的代码。这个需要一个填充值去初始化list的初始值。
   * 创建一个空的List，使用 `[]` 或者 `List.empty` 创建一个固定长度的List（或者 在运行时检测可增长性）
   * This constructor cannot be used in null-safe code.
   * Use [List.filled] to create a non-empty list.
   * This requires a fill value to initialize the list elements with.
   * To create an empty list, use `[]` for a growable list or
   * `List.empty` for a fixed length list (or where growability is determined
   * at run-time).
   */
  external factory List([int? length]);

    
    
  /**
  	  external factory List.filled(int length, E fill, {bool growable = false});
  
   * 根据传入的length创建一个List，并且使用[fill]填充每一个位置。
   * Creates a list of the given length with [fill] at each position.
   *
   * 这个length必须是一个非负整数。
   * The [length] must be a non-negative integer.
   *
   * 例如：
   * Example:
   * ```dart
   * new List<int>.filled(3, 0, growable: true); // [0, 0, 0]
   * ```
   *
   * 如果[growable]指定为false（默认值也是false），那么创建的List是固定长度的。如果[growable]指定为true，
   * 则创建可增长的List。
   * 如果List是可增长的，改变List的长度时，并不会用[fill]初始化新增的元素。
   * 在创建并且填充之后，这个List并不会不同于其他可增长或者固定长度的List创建使用。
   * 
   * 返回的数组的所有值，将共享相同的[fill]值。
   * The created list is fixed-length if [growable] is false (the default)
   * and growable if [growable] is true.
   * If the list is growable, changing its length will not initialize new
   * entries with [fill].
   * After being created and filled, the list is no different from any other
   * growable or fixed-length list created using [List].
   *
   * All elements of the returned list share the same [fill] value.
   * ```
   * var shared = new List.filled(3, []);
   * shared[0].add(499);
   * print(shared);  // => [[499], [499], [499]]
   * ```
   *
   * 你能使用[List.generate(length, (index) => null)]去创建一个List，并用一个新对象去填充每一个元素位置。
   * You can use [List.generate] to create a list with a new object at
   * each position.
   * ```
   * var unique = new List.generate(3, (_) => []);
   * unique[0].add(499);
   * print(unique); // => [[499], [], []]
   * ```
   */
  external factory List.filled(int length, E fill, {bool growable = false});

    
    
  /**
   *  List.empty({bool growable = false});
   * 
   * 创建一个空的List。
   * Creates a new empty list.
   * 如果[growable] 是 false （默认也是false值）, 这个List将会是固定长度，且长度为0的List。
   * 如果[growable] 是 true， 这个列表是可增长的 
   * the list is a fixed-length list of length zero.， 却等价于指定元素类型的空数组、
   
   * If [growable] is `false`, which is the default。
   * If [growable] is `true`, the list is growable and equivalent to `<E>[]`。
   */
  @Since("2.8")
  external factory List.empty({bool growable = false});

    
    
  /**
   * List.from(Iterable elements, {bool growable = true});
   * 
   * 创建一个包含所有元素的List。
   * 所有元素的迭代器提供这些元素的顺序。
   * 所有的元素，都将是[E]的实例。([E]就是泛型中传入的数据类型)
   * 这些可迭代的元素自身可能是任何元素类型，所以这个构造器常常用于向下类型转换为一个List.
   * 
   * 当[growable]参数为true时, 这个构造器创建一个可增长的List，否则返回一个固定长度的List。
   * 
   * Creates a list containing all [elements].
   * The [Iterator] of [elements] provides the order of the elements.
   * All the [elements] should be instances of [E].
   * The `elements` iterable itself may have any element type, so this
   * constructor can be used to down-cast a `List`, for example as:
   * ```dart
   * List<SuperType> superList = ...;
   * List<SubType> subList =
   *     new List<SubType>.from(superList.whereType<SubType>());
   * ```
   * This constructor creates a growable list when [growable] is true;
   * otherwise, it returns a fixed-length list.
   */
  external factory List.from(Iterable elements, {bool growable = true});

    
    
  /**
   * List.of(Iterable<E> elements, {bool growable = true});
   * 
   * 从一个Iterable对象为数据源，创建一个List.
   * 这个含有数据源的迭代器提供这些数据源的索引顺序。
   * 当[growable]参数为true时, 这个构造器创建一个可增长的List，否则返回一个固定长度的List。
   * 
   * 
   * Creates a list from [elements].
   *
   * The [Iterator] of [elements] provides the order of the elements.
   *
   * This constructor creates a growable list when [growable] is true;
   * otherwise, it returns a fixed-length list.
   */
  external factory List.of(Iterable<E> elements, {bool growable = true});

    
    
  /**
   * List.generate(int length, E generator(int index),
      {bool growable = true});
   * 
   * 创建一个含有多个元素的List。
   * 根据length参数创建一个List，并调用[generator]，在0~leng-1的返回内，、
   * 以递增的顺序为每个index位置的元素来填充value值。
   * 
   * Generates a list of values.
   *
   * Creates a list with [length] positions and fills it with values created by
   * calling [generator] for each index in the range `0` .. `length - 1`
   * in increasing order.
   * ```dart
   * List<int>.generate(3, (int index) => index * index); // [0, 1, 4]
   * ```
   * The created list is fixed-length if [growable] is set to false.
   *
   * The [length] must be non-negative.
   */
  external factory List.generate(int length, E generator(int index),
      {bool growable = true});

    
    
  /**
   * List.unmodifiable(Iterable elements);
   * 
   * 创建一个List，包含Iterable中的数据源，且不再允许修改。
   * Iterable中的数据源通过Iterator对象提供这些数据的索引顺序。
   * 一个不可修改的List，不能改变它的元素，以及List长度。
   * 如果元素自身是不可改变的，那么也会导致List是不可改变的。
   * 
   * 
   * Creates an unmodifiable list containing all [elements].
   *
   * The [Iterator] of [elements] provides the order of the elements.
   *
   * An unmodifiable list cannot have its length or elements changed.
   * If the elements are themselves immutable, then the resulting list
   * is also immutable.
   */
  external factory List.unmodifiable(Iterable elements);

    
    
  /**
   * static List<T> castFrom<S, T>(List<S> source) => CastList<S, T>(source);
   * 适配数据源[source] 成为一个 `List<T>`
   * 
   * 任何时候，这个列表将会生成一个不是[T]类型的元素， 这个元素访问将会被抛出。
   * 
   * 任何时候，一个[T]类型的值尝试存储到一个已经适配的List中。
   * 这个存储将会抛出，除非这个值也是[S]类型的一个实例。
   * 
   * 如果[source]中所有被访问的元素，实际上都是[T]类型的实例，而且如果所有元素被存储到返回的列表，
   * 这个列表中的元素实际上都是[T]类型的实例，那么这个返回的List可能会当做一个`List<T>`使用。 
   * 
   * Adapts [source] to be a `List<T>`.
   *
   * Any time the list would produce an element that is not a [T],
   * the element access will throw.
   *
   * Any time a [T] value is attempted stored into the adapted list,
   * the store will throw unless the value is also an instance of [S].
   *
   * If all accessed elements of [source] are actually instances of [T],
   * and if all elements stored into the returned list are actually instance
   * of [S],
   * then the returned list can be used as a `List<T>`.
   */
  static List<T> castFrom<S, T>(List<S> source) => CastList<S, T>(source);

    
    
  /**
   * static void copyRange<T>(List<T> target, int at, List<T> source,
   *   [int? start, int? end]) 
   *
   * 复制一个List的一个范围子数组到其它的数组。
   *  
   * 这是一个功能性的方法，通常被用于实现像[setRange]类似的方法
   * 
   * 这个范围从[start]到[end]，必须是个数据源[source]的有效范围，而且从指定位置的`end-start`有足够的空间。
   * 如果[start]不存在，那么默认为0；
   * 如果[end]不存在，那么默认为source.length.
   * 
   * 如果[source]与[target]是同一个list， 为了target的范围是包含source的返回的初始化内容作为结束 ，重叠source和target范围是好的做法。
   * 否则，元素复制的顺序是不能保证的。
   * 
   * 
   * 
   * Copy a range of one list into another list.
   *
   * This is a utility function that can be used to implement methods like
   * [setRange].
   *
   * The range from [start] to [end] must be a valid range of [source],
   * and there must be room for `end - start` elements from position [at].
   * If [start] is omitted, it defaults to zero.
   * If [end] is omitted, it defaults to [source.length].
   *
   * If [source] and [target] is the same list, overlapping source and target
   * ranges are respected so that the target range ends up containing the
   * initial content of the source range.
   * Otherwise the order of element copying is not guaranteed.
   */
  static void copyRange<T>(List<T> target, int at, List<T> source,
      [int? start, int? end]) {
    start ??= 0;
    end = RangeError.checkValidRange(start, end, source.length);
    if (end == null) {
      // TODO(dart-lang/language#440): Remove when promotion works.
      throw "unreachable";
    }
    int length = end - start;
    if (target.length < at + length) {
      throw ArgumentError.value(target, "target",
          "Not big enough to hold $length elements at position $at");
    }
    if (!identical(source, target) || start >= at) {
      for (int i = 0; i < length; i++) {
        target[at + i] = source[start + i];
      }
    } else {
      for (int i = length; --i >= 0;) {
        target[at + i] = source[start + i];
      }
    }
  }
    
    

  /**
   * static void writeIterable<T>(List<T> target, int at, Iterable<T> source)
   * 写入一个可迭代的对象的数据源到List中。
   * 
   * 这是一个功能性方法，常被用于实现像[setAll]方法。
   * 
   * 数据源[source]的所有数据，被写入到 [target]的指定位置。
   * 数据源[source]的长度不能长于[target]的长度。
   * 
   * 如果数据源[source]是一个列表，那么使用[copyRange]方法可能更加高效。
   * 
   * 
   * 
   * Write the elements of an iterable into a list.
   *
   * This is a utility function that can be used to implement methods like
   * [setAll].
   *
   * The elements of [source] are written into [target] from position [at].
   * The [source] must not contain more elements after writing the last
   * position of [target].
   *
   * If the source is a list, the [copyRange] function is likely to be more
   * efficient.
   */
  static void writeIterable<T>(List<T> target, int at, Iterable<T> source) {
    RangeError.checkValueInInterval(at, 0, target.length, "at");
    int index = at;
    int targetLength = target.length;
    for (var element in source) {
      if (index == targetLength) {
        throw IndexError(targetLength, target);
      }
      target[index] = element;
      index++;
    }
  }

    
    
  /**
   * List<R> cast<R>();
   * 返回这个List的视图，作为一个所有元素是[R]类型的实例的List。 
   * 
   * 如果这个List仅仅包含[R]类型的实例，所有读操作将会正确的工作。
   * 如果任何操作尝试访问一个非[R]类型的实例，这个访问将会被throw所替代。
   * 
   * 这个List，通过add，addAll添加元素，必须是[R]类型的实例作为有效参数给[add,addAll]函数。
   并且他们必须是[E]类型的实例，而被这个List所能接受。
   * 
   * 典型的实现就是 `List.castFrom<E, R>(this)`
   * 
   * 
   * 
   * 
   * Returns a view of this list as a list of [R] instances.
   *
   * If this list contains only instances of [R], all read operations
   * will work correctly. If any operation tries to access an element
   * that is not an instance of [R], the access will throw instead.
   *
   * Elements added to the list (e.g., by using [add] or [addAll])
   * must be instance of [R] to be valid arguments to the adding function,
   * and they must be instances of [E] as well to be accepted by
   * this list as well.
   *
   * Typically implemented as `List.castFrom<E, R>(this)`.
   */
  List<R> cast<R>();

    
    
  /**
   * E operator [](int index);
   * 返回List中指定index的元素。
   * 如果这个[index]越界，则会抛出一个[RangeError]错误。
   * 
   * Returns the object at the given [index] in the list
   * or throws a [RangeError] if [index] is out of bounds.
   */
  E operator [](int index);
    
    

  /**
   * void operator []=(int index, E value);
   * 根据[index]参数，将[value]设置到List的指定位置。
   * 
   * 如果[index]位置越界，那么抛出[RangeError]错误。
   * 
   * 
   * Sets the value at the given [index] in the list to [value]
   * or throws a [RangeError] if [index] is out of bounds.
   */
  void operator []=(int index, E value);
    
    

  /**
   * void set first(E value);
   * 更新List第一个位置的值。
   * 等价于 `list[0] = value`
   * 这个List不能为空。
   * 
   * 
   * Updates the first position of the list to contain [value].
   *
   * Equivalent to `theList[0] = value;`.
   *
   * The list must be non-empty.
   */
  void set first(E value);
    
    

  /**
   * void set last(E value);
   * 更新List的最后一个元素的值。 
   * 等价于 `theList[theList.length - 1] = value;`.
   * 这个List必须非空。
   * 
   * 
   * Updates the last position of the list to contain [value].
   *
   * Equivalent to `theList[theList.length - 1] = value;`.
   *
   * The list must be non-empty.
   */
  void set last(E value);

    
    
  /**
   * int get length;
   * 获取这个List中元素的数量。
   * 这个List中有效的index从[0]到[length-1]
   * 
   * 
   * The number of objects in this list.
   *
   * The valid indices for a list are `0` through `length - 1`.
   */
  int get length;
    
    

  /**
   * set length(int newLength);
   * 
   * 改变List的长度
   * 
   * 如果[newLength]的长度大于当前的[length],新增元素被初始化为null。
   * 如果新增的元素，不允许被赋值为null，那么新增长度将会失败。
   * 
   * 如果是固定长度的List看，或者其他增大List，但是不能用null初始化时，抛出一个[UnsupportedError]错误。
   * 
   * 
   * 
   * Changes the length of this list.
   *
   * If [newLength] is greater than
   * the current length, entries are initialized to `null`.
   * Increasing the length fails if the element type does not allow `null`.
   *
   * Throws an [UnsupportedError] if the list is fixed-length or
   * if attempting tp enlarge the list when `null` is not a valid element.
   */
  set length(int newLength);

    
    
  /**
   * void add(E value);
   * 增加一个元素到List的末尾。
   * 长度增1。
   * 
   * 如果是固定长度的List，则抛出一个[UnsupportedError]错误。
   * 
   * 
   * Adds [value] to the end of this list,
   * extending the length by one.
   *
   * Throws an [UnsupportedError] if the list is fixed-length.
   */
  void add(E value);

    
    
  /**
   * void addAll(Iterable<E> iterable);
   * 将一个可迭代的对象的数据源，追加到这个List的末尾。
   * 
   * 增加[iterable]数据源中元素的个数到这个List的[length]。
   * 如果这个List是固定长度的，那么抛出一个[UnsupportedError]错误。
   * 
   * 
   * Appends all objects of [iterable] to the end of this list.
   *
   * Extends the length of the list by the number of objects in [iterable].
   * Throws an [UnsupportedError] if this list is fixed-length.
   */
  void addAll(Iterable<E> iterable);

    
    
  /**
   * Iterable<E> get reversed;
   * 返回一个可迭代的对象；数据源是这个List的反向顺序的所有元素。
   * 
   * Returns an [Iterable] of the objects in this list in reverse order.
   */
  Iterable<E> get reversed;

    
    
  /**
   * void sort([int compare(E a, E b)?]);
   * 通过[compare]函数指定顺序，来排序这个List。
   * 
   * 这个[compare]函数必须作为一个比较器[comparator]来执行。
   * 
   * 如果[compare]被遗漏，那么默认的List实现是使用[Comparable.compare]. 
   * 
   * 一个比较器[Comparator], 用于比较对象如果相等返回0，甚至用于两个不同的对象。
   * 排序函数不能保证是稳定的，对于不同的对象， 做相等比较时，结果可能出现任何顺序。
   *
   * 
   *  
   * Sorts this list according to the order specified by the [compare] function.
   *
   * The [compare] function must act as a [Comparator].
   *
   *     List<String> numbers = ['two', 'three', 'four'];
   *     // Sort from shortest to longest.
   *     numbers.sort((a, b) => a.length.compareTo(b.length));
   *     print(numbers);  // [two, four, three]
   *
   * The default List implementations use [Comparable.compare] if
   * [compare] is omitted.
   *
   *     List<int> nums = [13, 2, -11];
   *     nums.sort();
   *     print(nums);  // [-11, 2, 13]
   *
   * A [Comparator] may compare objects as equal (return zero), even if they
   * are distinct objects.
   * The sort function is not guaranteed to be stable, so distinct objects
   * that compare as equal may occur in any order in the result:
   *
   *     List<String> numbers = ['one', 'two', 'three', 'four'];
   *     numbers.sort((a, b) => a.length.compareTo(b.length));
   *     print(numbers);  // [one, two, four, three] OR [two, one, four, three]
   */
  void sort([int compare(E a, E b)?]);

    
    
  /**
   *  void shuffle([Random? random]);
   *  随机打乱List的元素位置。（ 直接对该List生效。） 
   * 
   * Shuffles the elements of this list randomly.
   */
  void shuffle([Random? random]);

    
    
  /**
   *  int indexOf(E element, [int start = 0]);
   *  
   * 返回元素在List中的索引index。
   * 
   * 从List的开始到结束搜索， 第一次遇到这个元素，则返回该index。
   *     List<String> notes = ['do', 're', 'mi', 're'];
   *     notes.indexOf('re');    // 1
   *     notes.indexOf('re', 2); // 3
   * 如果元素在数组中不存在，则返回-1.
   * 
   * 
   * Returns the first index of [element] in this list.
   *
   * Searches the list from index [start] to the end of the list.
   * The first time an object [:o:] is encountered so that [:o == element:],
   * the index of [:o:] is returned.
   *     List<String> notes = ['do', 're', 'mi', 're'];
   *     notes.indexOf('re');    // 1
   *     notes.indexOf('re', 2); // 3
   *
   * Returns -1 if [element] is not found.
   *
   *     notes.indexOf('fa');    // -1
   */
  int indexOf(E element, [int start = 0]);

    
    
  /**
   * int indexWhere(bool test(E element), [int start = 0]);
   * 返回找到的第一个匹配到的元素的index。
   * 
   * 从指定的[start]索引开始搜索list， 返回遇到匿名函数返回true时的index。
   * 如果没有找到，那么就返回-1.
   * 
   * 
   * Returns the first index in the list that satisfies the provided [test].
   *
   * Searches the list from index [start] to the end of the list.
   * The first time an object `o` is encountered so that `test(o)` is true,
   * the index of `o` is returned.
   *
   * ```
   * List<String> notes = ['do', 're', 'mi', 're'];
   * notes.indexWhere((note) => note.startsWith('r'));       // 1
   * notes.indexWhere((note) => note.startsWith('r'), 2);    // 3
   * ```
   *
   * Returns -1 if [element] is not found.
   * ```
   * notes.indexWhere((note) => note.startsWith('k'));    // -1
   * ```
   */
  int indexWhere(bool test(E element), [int start = 0]);

    
    
  /**
   * 
   * int lastIndexWhere(bool test(E element), [int? start]);
   * 返回List中能被匹配的元素的最后一个元素的index。
   * 
   * 从List的[end]向前开始搜索，第一次匿名函数返回true则停止，且返回此时的index。
   * 如果[start]没有指定，那么默认为数组的[list.length]开始.
   * 
   * 如果元素没有被找到，那么就返回-1。
   * 
   * 
   * Returns the last index in the list that satisfies the provided [test].
   *
   * Searches the list from index [start] to 0.
   * The first time an object `o` is encountered so that `test(o)` is true,
   * the index of `o` is returned.
   * If [start] is omitted, it defaults to the [length] of the list.
   *
   * ```
   * List<String> notes = ['do', 're', 'mi', 're'];
   * notes.lastIndexWhere((note) => note.startsWith('r'));       // 3
   * notes.lastIndexWhere((note) => note.startsWith('r'), 2);    // 1
   * ```
   *
   * Returns -1 if [element] is not found.
   * ```
   * notes.lastIndexWhere((note) => note.startsWith('k'));    // -1
   * ```
   */
  int lastIndexWhere(bool test(E element), [int? start]);

    
    
  /**
   *  int lastIndexOf(E element, [int? start]);
   * 
   *  类似于indexOf,不过是从[list.length-1] - [0] 的搜索顺序。
   *  如果元素匹配到了就结束，且返回该index。
   *  如果没有匹配到，则返回-1。
   * 
   * 
   * Returns the last index of [element] in this list.
   *
   * Searches the list backwards from index [start] to 0.
   *
   * The first time an object [:o:] is encountered so that [:o == element:],
   * the index of [:o:] is returned.
   *
   *     List<String> notes = ['do', 're', 'mi', 're'];
   *     notes.lastIndexOf('re', 2); // 1
   *
   * If [start] is not provided, this method searches from the end of the
   * list.
   *
   *     notes.lastIndexOf('re');  // 3
   *
   * Returns -1 if [element] is not found.
   *
   *     notes.lastIndexOf('fa');  // -1
   */
  int lastIndexOf(E element, [int? start]);

    
    
  /**
   * void clear();
   * 清空列表， list的length直接置为0;
   * 如果是个固定长度的数组，那么不做处理，并且抛出 [UnsupportedError]错误。
   *  
   * 
   * Removes all objects from this list;
   * the length of the list becomes zero.
   *
   * Throws an [UnsupportedError], and retains all objects, if this
   * is a fixed-length list.
   */
  void clear();

    
    
  /**
   * void insert(int index, E element);
   * 
   * 插入一个对象到指定的位置。
   * 
   * List长度增加1， 该List中原来的index位置以及之后的元素，都后移一个位置。
   * List必须是可增长的。
   * 这个[index]必须是非负数，且不能大于[length]。
   * 
   * 
   * Inserts the object at position [index] in this list.
   *
   * This increases the length of the list by one and shifts all objects
   * at or after the index towards the end of the list.
   *
   * The list must be growable.
   * The [index] value must be non-negative and no greater than [length].
   */
  void insert(int index, E element);

    
    
  /**
   * void insertAll(int index, Iterable<E> iterable);
   * 通过[Iterable]的数据源，批量插入到List的指定位置。
   * 
   * List增加[iterable]的数据源个数对应的长度。并且原来index位置的元素以及之后的元素，向
   * List末尾移动指定长度的位置。
   * 
   * 这个List必须是可增长的。
   * 这个[index]的值必须是非负数，且布恩那个大于List的[length]。
   * 
   * 
   * Inserts all objects of [iterable] at position [index] in this list.
   *
   * This increases the length of the list by the length of [iterable] and
   * shifts all later objects towards the end of the list.
   *
   * The list must be growable.
   * The [index] value must be non-negative and no greater than [length].
   */
  void insertAll(int index, Iterable<E> iterable);

    
    
  /**
   * void setAll(int index, Iterable<E> iterable);
   * 
   * 使用iterable的数据源，覆盖List中的元素。从指定的List的[index]开始
   *     List<String> list = ['a', 'b', 'c'];
   *     list.setAll(1, ['bee', 'sea']);
   *     list.join(', '); // 'a, bee, sea'
   * 这个操作不会增加List的长度。
   * 这个[index]必须是非负数，而且不能大于[length]。
   * 这个[iterable]中元素的个数，不能大于list中[start, list.length]，否则抛异常。
   * 
   * 如果[iterable]是这个list本身的，那么在`setAll`期间，它的值可能发生改变。
   * 
   * 
   * Overwrites objects of `this` with the objects of [iterable], starting
   * at position [index] in this list.
   *
   *     List<String> list = ['a', 'b', 'c'];
   *     list.setAll(1, ['bee', 'sea']);
   *     list.join(', '); // 'a, bee, sea'
   *
   * This operation does not increase the length of `this`.
   *
   * The [index] must be non-negative and no greater than [length].
   *
   * The [iterable] must not have more elements than what can fit from [index]
   * to [length].
   *
   * If `iterable` is based on this list, its values may change /during/ the
   * `setAll` operation.
   */
  void setAll(int index, Iterable<E> iterable);

    
    
  /**
   *  bool remove(Object? value);
   *  删除list中首次被 value 参数所匹配到的元素。
   *  如果[value]在list中，那么返回true，否则返回false。
   *     List<String> parts = ['head', 'shoulders', 'knees', 'toes'];
   *     parts.remove('head'); // true
   *     parts.join(', ');     // 'shoulders, knees, toes'
   * 
   *   如果[value]不再list中，则不会有删除效果，且返回false。
   *   如果是固定长度的List，删除操作会报 [UnsupportedError] 错误。
   * 
   * 
   * 
   * Removes the first occurrence of [value] from this list.
   *
   * Returns true if [value] was in the list, false otherwise.
   *
   *     List<String> parts = ['head', 'shoulders', 'knees', 'toes'];
   *     parts.remove('head'); // true
   *     parts.join(', ');     // 'shoulders, knees, toes'
   *
   * The method has no effect if [value] was not in the list.
   *
   *     // Note: 'head' has already been removed.
   *     parts.remove('head'); // false
   *     parts.join(', ');     // 'shoulders, knees, toes'
   *
   * An [UnsupportedError] occurs if the list is fixed-length.
   */

  bool remove(Object? value);

    
    
  /**
   * E removeAt(int index);
   *
   * 根据一个索引从List中移除一个元素。
   * 这个方法List的[length]将会减1，并且移动该index后面的元素前移。
   * 返回一个被删除的元素。
   * 
   * 这个[index]必须在[0-length-1]之间。
   * 如果是个固定长度的List，删除操作会报 [UnsupportedError] 的错误。这种情况下，数组是不可修改的。
   * 
   * 
   * Removes the object at position [index] from this list.
   *
   * This method reduces the length of `this` by one and moves all later objects
   * down by one position.
   *
   * Returns the removed object.
   *
   * The [index] must be in the range `0 ≤ index < length`.
   *
   * Throws an [UnsupportedError] if this is a fixed-length list. In that case
   * the list is not modified.
   */
  E removeAt(int index);

    
    
  /**
   * E removeLast();
   * 弹出List中的最后一个元素。
   * 这个List必须不是空的，也不可以是固定长度的。
   * 
   * 
   * Pops and returns the last object in this list.
   *
   * The list must not be empty.
   *
   * Throws an [UnsupportedError] if this is a fixed-length list.
   */
  E removeLast();

    
    
  /**
   * void removeWhere(bool test(E element));
   * 移除所有匿名函数返回true时index对应的元素。（注意时所有被匹配的元素）
   *     List<String> numbers = ['one', 'two', 'three', 'four'];
   *     numbers.removeWhere((item) => item.length == 3);
   *     numbers.join(', '); // 'three, four'
   * 如果时固定长度，则抛出[UnsupportedError]
   * 
   * 
   * Removes all objects from this list that satisfy [test].
   *
   * An object [:o:] satisfies [test] if [:test(o):] is true.
   *
   *     List<String> numbers = ['one', 'two', 'three', 'four'];
   *     numbers.removeWhere((item) => item.length == 3);
   *     numbers.join(', '); // 'three, four'
   *
   * Throws an [UnsupportedError] if this is a fixed-length list.
   */
  void removeWhere(bool test(E element));

    
    
  /**
   * void retainWhere(bool test(E element));
   * 删除所有匿名函数返回false时index对应的元素。保留所有返回true的对象。
   *     An object [:o:] satisfies [test] if [:test(o):] is true.
   * 
   *     List<String> numbers = ['one', 'two', 'three', 'four'];
   *     numbers.retainWhere((item) => item.length == 3);
   *     numbers.join(', '); // 'one, two'
   * 如果时固定长度的List，将会抛出异常[UnsupportedError]
   * 
   * 
   * Removes all objects from this list that fail to satisfy [test].
   *
   * An object [:o:] satisfies [test] if [:test(o):] is true.
   *
   *     List<String> numbers = ['one', 'two', 'three', 'four'];
   *     numbers.retainWhere((item) => item.length == 3);
   *     numbers.join(', '); // 'one, two'
   *
   * Throws an [UnsupportedError] if this is a fixed-length list.
   */

    
    
  void retainWhere(bool test(E element));

  /**
   * List<E> operator +(List<E> other);
   * `操作就是： var list = list1 + list2 `
   *  
   * 返回这个List与另一个List的联合List，[other]中的元素以追加形式排在末尾。
   * Returns the concatenation of this list and [other].
   * 默认的行为是返回一个普通的可增长的List。一些List类型可以选择返回如他们自身一样类型的List。 
   *    
   * 
   * Returns a new list containing the elements of this list followed by
   * the elements of [other].
   *
   * The default behavior is to return a normal growable list.
   * Some list types may choose to return a list of the same type as themselves
   * (see [Uint8List.+]);
   */
  List<E> operator +(List<E> other);

    
    
  /**
   * List<E> sublist(int start, [int? end]);
   * 返回List的子subList，子subList的元素是从这个List的[start-end]复制元素，且元素顺序跟原来的List中元素顺序一致、  
   * ```dart
   *    var colors = ["red", "green", "blue", "orange", "pink"];
   *    print(colors.sublist(1, 3)); // [green, blue]
   * ```
   * 如果[end]被遗漏，那么它默认是这个List的[length]
   * [start],[end]必须在List的[0-length]范围内。
   * 如果[start] = [end],将会返回一个空数组。
   * 
   * 
   * Returns a new list containing the elements between [start] and [end].
   *
   * The new list is a `List<E>` containing the elements of this list at
   * positions greater than or equal to [start] and less than [end] in the same
   * order as they occur in this list.
   *
   * ```dart
   * var colors = ["red", "green", "blue", "orange", "pink"];
   * print(colors.sublist(1, 3)); // [green, blue]
   * ```
   *
   * If [end] is omitted, it defaults to the [length] of this list.
   *
   * ```dart
   * print(colors.sublist(1)); // [green, blue, orange, pink]
   * ```
   *
   * The `start` and `end` positions must satisfy the relations
   * 0 ≤ `start` ≤ `end` ≤ `this.length`
   * If `end` is equal to `start`, then the returned list is empty.
   */
  List<E> sublist(int start, [int? end]);

    
    
  /**
   * Iterable<E> getRange(int start, int end);
   *   
   * 返回一个[Iterable]对象，是List的[start, end]的一个子集。
   * 
   * 提供一个[start - end]的返回，在这次调用中必须是有效的(0<=start<=end<=length)。
   * 这个Range包含[start], 不包含[end].当然，如果[start]=[end]也是有效的，返回一个空的Iterable对象。
   * 
   * 返回的Iterable对象，行为像`skip(start).take(end - start)`.
   * 就是说，如果改变List的lengh，并不会因为这个Iterable而报错。
   * 
   * Returns an [Iterable] that iterates over the objects in the range
   * [start] inclusive to [end] exclusive.
   *
   * The provided range, given by [start] and [end], must be valid at the time
   * of the call.
   *
   * A range from [start] to [end] is valid if `0 <= start <= end <= len`, where
   * `len` is this list's `length`. The range starts at `start` and has length
   * `end - start`. An empty range (with `end == start`) is valid.
   *
   * The returned [Iterable] behaves like `skip(start).take(end - start)`.
   * That is, it does *not* throw if this list changes size.
   *
   *     List<String> colors = ['red', 'green', 'blue', 'orange', 'pink'];
   *     Iterable<String> range = colors.getRange(1, 4);
   *     range.join(', ');  // 'green, blue, orange'
   *     colors.length = 3;
   *     range.join(', ');  // 'green, blue'
   */
  Iterable<E> getRange(int start, int end);

    
    
  /**
   * void setRange(int start, int end, Iterable<E> iterable, [int skipCount = 0]);
   * 
   * 复制Iterable的对象，跳过Iterable的[0-skipCount]位置的元素，批量复制数据元素到List中的[start, end]中、
   * 
   * 这个被提供的range，通过[start, end]指定，且[start, end]必须是有效的,即[0<=start<=end<=list.length]。
   * 当然，如果[end==start]时，有效且返回一个空数据的Iterable对象。
   * 
   * [iterable]对象在跳过[0-skipCount]返回的元素之后，必须要有足够的对象来填充List[start-end]范围。
   * 
   * 如果 Iterable就是这个List， 即使两个ranges重叠，[setRange]操作[skipCount, skipCount+(end-start)] 的原始的元素会
   * 复制到[start, end]中。
   * 
   * 如果[iterable]在某些其它的方式上依赖这个List， 不保证可行。
   * 
   * 
   * Copies the objects of [iterable], skipping [skipCount] objects first,
   * into the range [start], inclusive, to [end], exclusive, of the list.
   *
   *     List<int> list1 = [1, 2, 3, 4];
   *     List<int> list2 = [5, 6, 7, 8, 9];
   *     // Copies the 4th and 5th items in list2 as the 2nd and 3rd items
   *     // of list1.
   *     list1.setRange(1, 3, list2, 3);
   *     list1.join(', '); // '1, 8, 9, 4'
   *
   * The provided range, given by [start] and [end], must be valid.
   * A range from [start] to [end] is valid if `0 <= start <= end <= len`, where
   * `len` is this list's `length`. The range starts at `start` and has length
   * `end - start`. An empty range (with `end == start`) is valid.
   *
   * The [iterable] must have enough objects to fill the range from `start`
   * to `end` after skipping [skipCount] objects.
   *
   * If `iterable` is this list, the operation copies the elements
   * originally in the range from `skipCount` to `skipCount + (end - start)` to
   * the range `start` to `end`, even if the two ranges overlap.
   *
   * If `iterable` depends on this list in some other way, no guarantees are
   * made.
   */
  void setRange(int start, int end, Iterable<E> iterable, [int skipCount = 0]);

    
    
  /**
   *   void removeRange(int start, int end);
   *  删除一个指定范围[start, end]内的所有元素。
   *  提供的[start], [end]必须在[0-length]范围内。
   * 
   * 
   * Removes the objects in the range [start] inclusive to [end] exclusive.
   *
   * The provided range, given by [start] and [end], must be valid.
   * A range from [start] to [end] is valid if `0 <= start <= end <= len`, where
   * `len` is this list's `length`. The range starts at `start` and has length
   * `end - start`. An empty range (with `end == start`) is valid.
   *
   * Throws an [UnsupportedError] if this is a fixed-length list. In that case
   * the list is not modified.
   */
  void removeRange(int start, int end);

    
    
  /**
   * void fillRange(int start, int end, [E? fillValue]);
   * 
   * 对List中的指定返回[start, end]使用指定元素进行填充。
   * 提供的[start], [end]必须在[0-length]范围内。
   * 
   * 如果元素的类型不能赋值null，忽略[fillValue]或者输入null, 那么将会执行失败。
   * 
   * 
   * Sets the objects in the range [start] inclusive to [end] exclusive
   * to the given [fillValue].
   *
   * The provided range, given by [start] and [end], must be valid.
   * A range from [start] to [end] is valid if `0 <= start <= end <= len`, where
   * `len` is this list's `length`. The range starts at `start` and has length
   * `end - start`. An empty range (with `end == start`) is valid.
   *
   * Example:
   * ```dart
   *  List<int> list = new List(3);
   *     list.fillRange(0, 2, 1);
   *     print(list); //  [1, 1, null]
   * ```
   *
   * If the element type is not nullable, omitting [fillValue] or passing `null`
   * as [fillValue] will make the `fillRange` fail.
   */
  void fillRange(int start, int end, [E? fillValue]);

    
    
  /**
   * void replaceRange(int start, int end, Iterable<E> replacement);
   *  
   * 删除List[start, end]范围内的所有元素，然后将Iterable中的所有元素插入。
   * 
   * 这个方法不能工作在固定长度的List上，即使是相同元素的个数被替换。如果有那种情形，
   * 建议使用[setRange]。
   * 
   * 
   * Removes the objects in the range [start] inclusive to [end] exclusive
   * and inserts the contents of [replacement] in its place.
   *
   *     List<int> list = [1, 2, 3, 4, 5];
   *     list.replaceRange(1, 4, [6, 7]);
   *     list.join(', '); // '1, 6, 7, 5'
   *
   * The provided range, given by [start] and [end], must be valid.
   * A range from [start] to [end] is valid if `0 <= start <= end <= len`, where
   * `len` is this list's `length`. The range starts at `start` and has length
   * `end - start`. An empty range (with `end == start`) is valid.
   *
   * This method does not work on fixed-length lists, even when [replacement]
   * has the same number of elements as the replaced range. In that case use
   * [setRange] instead.
   */
  void replaceRange(int start, int end, Iterable<E> replacement);

    
    
  /**
   * Map<int, E> asMap();
   * 
   * 返回一个不可修改的[Map].
   * 
   * 这个map使用List的索引作为Key和对应的元素作为value。
   * `使用Map.keys`获取到的[Iterable]对象通过数字顺序迭代这个列表的索引集合。
   * 
   * Returns an unmodifiable [Map] view of `this`.
   *
   * The map uses the indices of this list as keys and the corresponding objects
   * as values. The `Map.keys` [Iterable] iterates the indices of this list
   * in numerical order.
   *
   *     List<String> words = ['fee', 'fi', 'fo', 'fum'];
   *     Map<int, String> map = words.asMap();
   *     map[0] + map[1];   // 'feefi';
   *     map.keys.toList(); // [0, 1, 2, 3]
   */
  Map<int, E> asMap();

    
    
  /**
   * bool operator ==(Object other);
   * 
   * 判断一个List是否与另外一个List相等。 
   * 默认情况下， List是等于它们自身的。
   * 即使[other]也是一个List，相等性比较也不是比较两个List的元素。
   * 
  * Whether this list is equal to [other].
  *
  * Lists are, by default, only equal to themselves.
  * Even if [other] is also a list, the equality comparison
  * does not compare the elements of the two lists.
  */
  bool operator ==(Object other);
}

```



## Set

### Set dart Api 文件翻译

```dart
/**
 * 每一个对象只能出现一次的对象集合。
 * A collection of objects in which each object can occur only once.
 *
 * 那就是说， 对于每一个元素类型的对象， 这个对象或被考虑放到set中，或者不放到set中。
 * That is, for each object of the element type, the object is either considered
 * to be in the set, or to _not_ be in the set.
 *
 * Set实现可能考虑一些难以区分的元素。在set中，这些元素被当做任何操作都是相同的处理过。
 * Set implementations may consider some elements indistinguishable. These
 * elements are treated as being the same for any operation on the set.
 *
 * 默认的Set实现是[linkedHashSet]，如果元素对象使用--操作是相等的，就认为对象是难以区分的。
 * The default [Set] implementation, [LinkedHashSet], considers objects
 * indistinguishable if they are equal with regard to
 * operator [Object.==].
 *
 * 迭代一个set中的元素，在某些方式上可能是无序或者有序的。比如：
 * Iterating over elements of a set may be either unordered
 * or ordered in some way. Examples:
 *
 * [HashSet]是无序的， 以为这它的迭代顺序是没有指定的。、
 * [LinkedHashSet]通过元素的插入顺序进行迭代。一个排序的Set，像[splayTreeSet]根据
 * 排序顺序进行迭代。
 * * A [HashSet] is unordered, which means that its iteration order is
 *   unspecified,
 * * [LinkedHashSet] iterates in the insertion order of its elements, and
 * * a sorted set like [SplayTreeSet] iterates the elements in sorted order.
 *
 * 当一个在集合中的操作正在执行时（比如调用[forEach]或者[containsAll]方法），通常是不允许修改
 * 集合的（增加或者删除元素）。当迭代这个Set自身，或者任何由这个Set返回的[Iterable]对象，都不允许去
 * 修改Set（增加或者删除元素），比如通过像[where], [map]等方法返回的[Iterable]对象
 * It is generally not allowed to modify the set (add or remove elements) while
 * an operation on the set is being performed, for example during a call to
 * [forEach] or [containsAll]. Nor is it allowed to modify the set while
 * iterating either the set itself or any [Iterable] that is backed by the set,
 * such as the ones returned by methods like [where] and [map].
 *
 * 
 * Set中的元素，通常是不允许去修改元素的相等性，比如它们的hashcode。一些专门的子类可能更随意些，
 * 这种情形应该用文档标识这种行为。
 * It is generally not allowed to modify the equality of elements (and thus not
 * their hashcode) while they are in the set. Some specialized subtypes may be
 * more permissive, in which case they should document this behavior.
 */
abstract class Set<E> extends EfficientLengthIterable<E> {
  /**
   * factory Set() = LinkedHashSet<E>;
   * 
   * 创建一个空的[Set].
   * 被创建的[Set]是一个简单的[LinkedHashSet].
   * 列如：它认为元素通过==是难以区分的，需要让它们有一个兼容的[Object.hashCode]实现。
   * 
   * 这个Set的相同
   * 
   * Creates an empty [Set].
   *
   * The created [Set] is a plain [LinkedHashSet].
   * As such, it considers elements that are equal (using [operator ==]) to be
   * indistinguishable, and requires them to have a compatible
   * [Object.hashCode] implementation.
   *
   * 集合相等判断由 `LinkedHashSet`提供。
   * The set is equivalent to one created by `new LinkedHashSet<E>()`.
   */
  factory Set() = LinkedHashSet<E>;

  /**
   * factory Set.identity() = LinkedHashSet<E>.identity;
   * 
   * 创建一个空的带有身份的[Set]
   * 创建的集合[Set]是一个使用id作为相等关系的[LinkedHashSet]
   * 这个[Set]的相等性判断由`new LinkedHashSet<E>.identity()`提供。
   * 
   * Creates an empty identity [Set].
   *
   * The created [Set] is a [LinkedHashSet] that uses identity as equality
   * relation.
   *
   * The set is equivalent to one created by `new LinkedHashSet<E>.identity()`.
   */
  factory Set.identity() = LinkedHashSet<E>.identity;

  /**
   * factory Set.from(Iterable elements) = LinkedHashSet<E>.from;
   * 
   * 创建一个包含[Iterable]数据源的[Set]。
   * Creates a [Set] that contains all [elements].
   *
   * 所有的元素必须是[E]类型的实例。
   * 这个迭代自身的Iterable,能够拥有任何元素类型。所以这个构造器常常降级为一个Set。
   * 比如如下：
   *     Set<SuperType> superSet = ...;
   *     Set<SubType> subSet =
   *         new Set<SubType>.from(superSet.where((e) => e is SubType));
   * 这个被创造的[Set]是一个[LinkedHashSet]. 比如，它认为元素的相等判断使用==是难以区分的，
   * 需要它们有一个合适的[Object.hashCode]实现。
   * 这个集合的相等性判断由`new LinkedHashSet<E>.from(elements)`提供。
   * 
   * 
   * All the [elements] should be instances of [E].
   * The `elements` iterable itself can have any type,
   * so this constructor can be used to down-cast a `Set`, for example as:
   *
   *     Set<SuperType> superSet = ...;
   *     Set<SubType> subSet =
   *         new Set<SubType>.from(superSet.where((e) => e is SubType));
   *
   * The created [Set] is a [LinkedHashSet]. As such, it considers elements that
   * are equal (using [operator ==]) to be indistinguishable, and requires them to
   * have a compatible [Object.hashCode] implementation.
   *
   * The set is equivalent to one created by
   * `new LinkedHashSet<E>.from(elements)`.
   */
  factory Set.from(Iterable elements) = LinkedHashSet<E>.from;

  /**
   * factory Set.of(Iterable<E> elements) = LinkedHashSet<E>.of;
   * 
   * 根据一个Iterable的数据源创建一个[Set].
   * 被创建的[Set]是一个[LinkedHashSet]对象。
   * 
   * 这个被创造的[Set]是一个[LinkedHashSet]. 比如，它认为元素的相等判断使用==是难以区分的，
   * 需要它们有一个合适的[Object.hashCode]实现。
   * 这个集合的相等性判断由`new LinkedHashSet<E>.of(elements)`提供。
   * 
   * 
   * 
   * Creates a [Set] from [elements].
   *
   * The created [Set] is a [LinkedHashSet]. As such, it considers elements that
   * are equal (using [operator ==]) to be indistinguishable, and requires them to
   * have a compatible [Object.hashCode] implementation.
   *
   * The set is equivalent to one created by
   * `new LinkedHashSet<E>.of(elements)`.
   */
  factory Set.of(Iterable<E> elements) = LinkedHashSet<E>.of;

  /**
   * static Set<T> castFrom<S, T>(Set<S> source, {Set<R> Function<R>()? newSet}) =>
      CastSet<S, T>(source, newSet);
   * 
   * 适配source的数据源，转成一个 [Set<T>]
   * Adapts [source] to be a `Set<T>`.
   * 
   * 
   *如果新的集合被提供，它常被用于创造一个新的sets，并当做[toSet],[union]返回, 也被用于
   * 交集和差集。如果[newSet]被忽略，它默认会使用默认的[Set]构造器来创建一个set，且交集和差集返回一个在source对象
   * 上调用同样方法的适配的版本。

   * If [newSet] is provided, it is used to create the new sets returned
   * by [toSet], [union], and is also used for [intersection] and [difference].
   * If [newSet] is omitted, it defaults to creating a new set using the
   * default [Set] constructor, and [intersection] and [difference]
   * returns an adapted version of calling the same method on the source.
   *
   * 任何时候，Set将生成一个元素不是[T]类型的元素，这个元素访问时将会抛出错误.
   * Any time the set would produce an element that is not a [T],
   * the element access will throw.
   *
   * 任何时候一个[T]类型的值尝试增加到一个适配的Set，除非这个value也是[S]类型的实例，
   * 否则存储时会抛出异常。
   * Any time a [T] value is attempted added into the adapted set,
   * the store will throw unless the value is also an instance of [S].
   *
   * 如果所有被访问的source中的元素，实际上是[T]类型的元素， 并且如果所有添加到要返回的SEt的元素
   * 实际上都是[S]类型的实例，那么返回的set通常是`Set<T>`.
   * If all accessed elements of [source] are actually instances of [T],
   * and if all elements added to the returned set are actually instance
   * of [S],
   * then the returned set can be used as a `Set<T>`.
   */
  static Set<T> castFrom<S, T>(Set<S> source, {Set<R> Function<R>()? newSet}) =>
      CastSet<S, T>(source, newSet);

  /**
   * Set<R> cast<R>();
   * 提供一个sSet的视图，作为一个[R]类型的元素的Set集合。
   * 
   * 如果这个Set仅仅包含[R]类型的实例，所有读操作将会工作正常。如果其他操作尝试起访问一个不是
   * [R]类型实例的元素，访问将会抛出异常。
   * 
   * 元素通过add()，addAll()等方法添加到集合Set中，必须是一个[R]类型的实例的有效参数传入到addh函数中，
   * 并且，必须是[E]类型的实例，以及能被这个Set所能接受。
   * 
   * Provides a view of this set as a set of [R] instances.
   *
   * If this set contains only instances of [R], all read operations
   * will work correctly. If any operation tries to access an element
   * that is not an instance of [R], the access will throw instead.
   *
   * Elements added to the set (e.g., by using [add] or [addAll])
   * must be instance of [R] to be valid arguments to the adding function,
   * and they must be instances of [E] as well to be accepted by
   * this set as well.
   */
  Set<R> cast<R>();

  /**
   * Iterator<E> get iterator;
   * 提供一个迭代器，用于迭代set集合中的元素。
   * 
   * 迭代器的顺序被个别的[Set]实现所定义，但是在集合的更改上保持一致。
   * 
   * Provides an iterator that iterates over the elements of this set.
   *
   * The order of iteration is defined by the individual `Set` implementation,
   * but must be consistent between changes to the set.
   */
  Iterator<E> get iterator;

  /**
   * bool contains(Object? value);
   * 如果value在这个集合中则返回true， 否则返回false；
   * 
   * Returns true if [value] is in the set.
   */
  bool contains(Object? value);

  /**
   * bool add(E value);
   * 增加元素到set中。
   * 如果这个value还不在这个set中，则返回true，否则返回false，且集合不做任何改变。
   * 
   * Adds [value] to the set.
   *
   * Returns `true` if [value] (or an equal value) was not yet in the set.
   * Otherwise returns `false` and the set is not changed.
   *
   * Example:
   *
   *     var set = new Set();
   *     var time1 = new DateTime.fromMillisecondsSinceEpoch(0);
   *     var time2 = new DateTime.fromMillisecondsSinceEpoch(0);
   *     // time1 and time2 are equal, but not identical.
   *     Expect.isTrue(time1 == time2);
   *     Expect.isFalse(identical(time1, time2));
   *     set.add(time1);  // => true.
   *     // A value equal to time2 exists already in the set, and the call to
   *     // add doesn't change the set.
   *     set.add(time2);  // => false.
   *     Expect.isTrue(set.length == 1);
   *     Expect.isTrue(identical(time1, set.first));
   */
  bool add(E value);

  /**
   * void addAll(Iterable<E> elements);
   * 增加Iterable中数据源的所有元素到这个集合中。
   * 
   * 等价于将每一个元素使用add()方法添加，但是有的集合可能会优化它。
   * 
   * 
   * Adds all [elements] to this Set.
   *
   * Equivalent to adding each element in [elements] using [add],
   * but some collections may be able to optimize it.
   */
  void addAll(Iterable<E> elements);

  /**
   * bool remove(Object? value);
   * 删除集合中的value值。
   * 如果value存在于集合中，那么删除并且返回true。否则返回false，且集合不做删除。
   * 
   * 
   * Removes [value] from the set. Returns true if [value] was
   * in the set. Returns false otherwise. The method has no effect
   * if [value] value was not in the set.
   */
  bool remove(Object? value);

  /**
   * E? lookup(Object? object);
   * 如果一个对象在集合中，那么返回它。
   * 检查一个对下你给是否在set中，像[contains]方法，如果是的话，则返回集合中的object对象，
   * 否则返回null。
   * 
   * 如果被set使用的等价关系，没有id， 那么这个返回的对象是无`identical`的对象，
   * 一些集合实现可能不会去实现这个方法。
   * 如果[contains]方法是计算的，而不是基于一个实际的对象实例，那么不会有专门表现这个set元素的实例对象
   * 
   * If an object equal to [object] is in the set, return it.
   *
   * Checks whether [object] is in the set, like [contains], and if so,
   * returns the object in the set, otherwise returns `null`.
   *
   * If the equality relation used by the set is not identity,
   * then the returned object may not be *identical* to [object].
   * Some set implementations may not be able to implement this method.
   * If the [contains] method is computed,
   * rather than being based on an actual object instance,
   * then there may not be a specific object instance representing the
   * set element.
   */
  E? lookup(Object? object);

  /**
   * void removeAll(Iterable<Object?> elements);
   * 移除Set中Iterable中含有的元素。
   * 
   * Removes each element of [elements] from this set.
   */
  void removeAll(Iterable<Object?> elements);

  /**
   * void retainAll(Iterable<Object?> elements);
   * 移除Set中，且Iterable数据源中没有的元素。
   * 
   * 检查Iterable中的每一个元素，是否有元素与存在于集合的元素相等(通过contains方法判断)，
   * 如果这样的话，在集合中相等的元素将会被保留， 不等于Iterable中任何元素的List中的元素将会
   * 被移除。
   * 
   * 
   * Removes all elements of this set that are not elements in [elements].
   *
   * Checks for each element of [elements] whether there is an element in this
   * set that is equal to it (according to `this.contains`), and if so, the
   * equal element in this set is retained, and elements that are not equal
   * to any element in `elements` are removed.
   */
  void retainAll(Iterable<Object?> elements);

  /**
   * void removeWhere(bool test(E element));
   * 移除满足[test]方法的所有在Set集合中的元素。
   * 
   * Removes all elements of this set that satisfy [test].
   */
  void removeWhere(bool test(E element));

  /**
   * void retainWhere(bool test(E element));
  * 移除不满足[test]方法的所有在Set集合中的元素。
   * 
   * Removes all elements of this set that fail to satisfy [test].
   */
  void retainWhere(bool test(E element));

  /**
   * bool containsAll(Iterable<Object?> other);
   * 判断Set是否含有Iterable数据源中所有的元素，如果全部包含，则返回true，否则返回false。
   * 
   * Returns whether this Set contains all the elements of [other].
   */
  bool containsAll(Iterable<Object?> other);

  /**
   * Set<E> intersection(Set<Object?> other);
   * 返回一个Set本身，与其它Set的交集。
   * 那就是说，这个返回的 Set 包含的所有元素既在 这个Set对象中，也在other set对象中。
   * 简而言之，就是取交集。
   * 
   * 
   * Returns a new set which is the intersection between this set and [other].
   *
   * That is, the returned set contains all the elements of this [Set] that
   * are also elements of [other] according to `other.contains`.
   */
  Set<E> intersection(Set<Object?> other);

  /**
   * Set<E> union(Set<E> other);
   * 取并集，返回一个新的集合，这个集合包含 set本身，以及other set的所有元素。
   * 那就是说，返回的set 包含了 两个set的所有元素。
   * 
   * Returns a new set which contains all the elements of this set and [other].
   *
   * That is, the returned set contains all the elements of this [Set] and
   * all the elements of [other].
   */
  Set<E> union(Set<E> other);

  /**
   * Set<E> difference(Set<Object?> other);
   * 
   * 取差集， 返回一个新的集合，这个集合的元素在 set本身中存在，但是都不在other set中存在。
   * 
   * Returns a new set with the elements of this that are not in [other].
   *
   * That is, the returned set contains all the elements of this [Set] that
   * are not elements of [other] according to `other.contains`.
   */
  Set<E> difference(Set<Object?> other);

  /**
   * void clear();
   * 清除集合中所有的元素。
   * 
   * Removes all elements in the set.
   */
  void clear();

  /* 
    Set<E> toSet();
    用相同的元素创建一个set对象，行为像这个set本身。
    关于增加和删除元素的行为是相同的，它初始化包含相同的元素。
    如果它指定了一个元素的顺序，返回的set中元素也是同样的顺序。

    Creates a [Set] with the same elements and behavior as this `Set`.
   *
   * The returned set behaves the same as this set
   * with regard to adding and removing elements.
   * It initially contains the same elements.
   * If this set specifies an ordering of the elements,
   * the returned set will have the same order.
   */
  Set<E> toSet();
}
```



## Map

## Map dart api 文件翻译

```dart
// Copyright (c) 2011, the Dart project authors.  Please see the AUTHORS file
// for details. All rights reserved. Use of this source code is governed by a
// BSD-style license that can be found in the LICENSE file.

part of dart.core;

/**
 * 一个含有key-value对的集合， 使用它相关联的key取回value。
 * 
 * map中的key是有限的个数，并且每一个key必须是精确的一个value关联。
 * 
 * Maps，它的keys集合， values集合，都可以迭代。
 * 迭代的顺序根据不同的map类型的实现而定义。比如:
 *    简单的 [HashMap] 是无序的，没有顺序可以保证。
 *    [LinkedHashMap] 根据插入的顺序进行迭代。
 *    一个排序好的map，像[SplayTreeMap]根据排序顺序迭代keys。
 * 当一个操作在map中执行时，比如函数调用，在[forEach], [putIfAbsent]调用时，通常
 * 是不被允许修改map（删除，增加keys）。
 * 当迭代key或者value时，修改map，也可能打断迭代。
 * 
 * 当元素在map中时，通常不会允许修改keys的相等性，一些专门的子类可能宽松些，在这些案例中，
 * 他们必须用文档标识出这些行文。
 * 
 * 
 * A collection of key/value pairs, from which you retrieve a value
 * using its associated key.
 *
 * There is a finite number of keys in the map,
 * and each key has exactly one value associated with it.
 *
 * Maps, and their keys and values, can be iterated.
 * The order of iteration is defined by the individual type of map.
 * Examples:
 *
 * * The plain [HashMap] is unordered (no order is guaranteed),
 * * the [LinkedHashMap] iterates in key insertion order,
 * * and a sorted map like [SplayTreeMap] iterates the keys in sorted order.
 *
 * It is generally not allowed to modify the map (add or remove keys) while
 * an operation is being performed on the map, for example in functions called
 * during a [forEach] or [putIfAbsent] call.
 * Modifying the map while iterating the keys or values
 * may also break the iteration.
 *
 * It is generally not allowed to modify the equality of keys (and thus not
 * their hashcode) while they are in the map. Some specialized subtypes may be
 * more permissive, in which case they should document this behavior.
 */
abstract class Map<K, V> {
  /**
   * external factory Map();
   *  
   * 创建一个Map实例，默认实现是[LinkedHashMap]实例。
   * 
   * 这个构造器等价于非常量的 map 字面量 `<k, v>{}`
   * 
   * `LinkedHashMap`需要实现了合适的`operator==`和`hashCode`的，并且允许使用null作为key的
   * keys集合。它按照key的插入顺序进行迭代。
   * 
   * 
   * Creates a Map instance with the default implementation, [LinkedHashMap].
   *
   * This constructor is equivalent to the non-const map literal `<K,V>{}`.
   *
   * A `LinkedHashMap` requires the keys to implement compatible
   * `operator==` and `hashCode`, and it allows null as a key.
   * It iterates in key insertion order.
   */
  external factory Map();

  /**
   * Map.from(Map other) = LinkedHashMap<K, V>.from;
   * 创建一个[LinkedHashMap]实例，并且包含 other map的所有 key-value对。
   * 
   * 这些key必须是[k]类型的实例，且value是[V]类型的实例。other map自身必须可以拥有任何类型。
   * 
   * `LinkedHashMap`需要实现了合适的`operator==`和`hashCode`的，并且允许使用null作为key的
   * keys集合。它按照key的插入顺序进行迭代。
   * 
   * 
   * Creates a [LinkedHashMap] instance that contains all key/value pairs of
   * [other].
   *
   * The keys must all be instances of [K] and the values of [V].
   * The [other] map itself can have any type.
   *
   * A `LinkedHashMap` requires the keys to implement compatible
   * `operator==` and `hashCode`, and it allows `null` as a key.
   * It iterates in key insertion order.
   */
  factory Map.from(Map other) = LinkedHashMap<K, V>.from;

  /**
   * Map.of(Map<K, V> other) = LinkedHashMap<K, V>.of;
   * 创建一个[LinkedHashMap]实例，并且包含 other map的所有 key-value对。
   * 
   * 这些key必须是[k]类型的实例，且value是[V]类型的实例。other map自身必须可以拥有任何类型。
   * 
   * `LinkedHashMap`需要实现了合适的`operator==`和`hashCode`的，并且允许使用null作为key的
   * keys集合。它按照key的插入顺序进行迭代。
   * 
   * 
   * Creates a [LinkedHashMap] with the same keys and values as [other].
   *
   * A `LinkedHashMap` requires the keys to implement compatible
   * `operator==` and `hashCode`, and it allows `null` as a key.
   * It iterates in key insertion order.
   */
  factory Map.of(Map<K, V> other) = LinkedHashMap<K, V>.of;

  /**
   * Map.unmodifiable(Map<dynamic, dynamic> other);
   * 创建一个不可修改的hash基础的base，包含other map的所有key-value对。
   * 
   * 这些key必须是[K]类型的实例，而value必须是[v]类型的实例。other map自身可以包含任何类型。
   * 
   * `LinkedHashMap`需要实现了合适的`operator==`和`hashCode`的，并且允许使用null作为key的
   * keys集合。它按照key的插入顺序进行迭代。被创建的map以固定的顺序迭代keys，保存other map提供的顺序。
   * 
   * 这个结果map行为像 Map.from的结果，除了这个map通过构造器返回的是不可修改的。
   * 
   * 
   * Creates an unmodifiable hash based map containing the entries of [other].
   *
   * The keys must all be instances of [K] and the values of [V].
   * The [other] map itself can have any type.
   *
   * The map requires the keys to implement compatible
   * `operator==` and `hashCode`, and it allows `null` as a key.
   * The created map iterates keys in a fixed order,
   * preserving the order provided by [other].
   *
   * The resulting map behaves like the result of [Map.from],
   * except that the map returned by this constructor is not modifiable.
   */
  external factory Map.unmodifiable(Map<dynamic, dynamic> other);

  /**
   * factory Map.identity() = LinkedHashMap<K, V>.identity;
   * 用默认的实现创建一个含有ID的map [LinkedHashMap]。
   * 
   * 一个ID map 使用 [identical]方法判断相等，且 使用keys的hashcode的 [identityHashCode]
   * 来代替==操作和[Object.hashCode].
   * 返回的map允许使用 `null` 作为 key值。
   * 这个map的迭代顺序根据key的插入顺序。
   * 
   * 
   * 
   * Creates an identity map with the default implementation, [LinkedHashMap].
   *
   * An identity map uses [identical] for equality and [identityHashCode]
   * for hash codes of keys instead of the intrinsic [Object.operator==] and
   * [Object.hashCode] of the keys.
   *
   * The returned map allows `null` as a key.
   * It iterates in key insertion order.
   */
  factory Map.identity() = LinkedHashMap<K, V>.identity;

  /**
   * factory Map.fromIterable(Iterable iterable,
      {K key(element)?, V value(element)?}) = LinkedHashMap<K, V>.fromIterable;
   * 
   * 创建一个Map实例， 它的keys-values都是从iterable的数据源中获取，并且属性是计算型的。
   * 创建的map是一个[LinkedHashMap]类型的实例。
   * `LinkedHashMap`实例需要的key值，实现合适的==以及hashcode，并且它允许key值为null，
   * 它根绝插入顺序进行迭代。
   * 
   * 对于Iterable数据源的每一个元素，通过各自申请key-value,这个构造器计算每一对key-value对.
   * 
   * 下面的例子从List中创建一个新的Map。这个map的keys是list的value值转换成字符串，map的value
   * 是list的值的平方。
   * 
   *     List<int> list = [1, 2, 3];
   *     Map<String, int> map = new Map.fromIterable(list,
   *         key: (item) => item.toString(),
   *         value: (item) => item * item);
   *
   *     map['1'] + map['2']; // 1 + 4
   *     map['3'] - map['2']; // 9 - 4
   * 
   * 如果对于key-value如果没有值被指定，那么默认值是一个id函数。
   * 在接下来的例子中， map 的这些 keys 和对应的 values 是 List 的 values值。
   *     map = new Map.fromIterable(list);
   *     map[1] + map[2]; // 1 + 2
   *     map[3] - map[2]; // 3 - 2
   * 通过iterable数据源获取的计算属性的keys，不需要key是唯一的。这个最后出现的可以、
   * 将会简单的覆盖任何之前的值。
   * 
   * 
   * 
   * Creates a Map instance in which the keys and values are computed from the
   * [iterable].
   *
   * The created map is a [LinkedHashMap].
   * A `LinkedHashMap` requires the keys to implement compatible
   * `operator==` and `hashCode`, and it allows null as a key.
   * It iterates in key insertion order.
   *
   * For each element of the [iterable] this constructor computes a key/value
   * pair, by applying [key] and [value] respectively.
   *
   * The example below creates a new Map from a List. The keys of `map` are
   * `list` values converted to strings, and the values of the `map` are the
   * squares of the `list` values:
   *
   *     List<int> list = [1, 2, 3];
   *     Map<String, int> map = new Map.fromIterable(list,
   *         key: (item) => item.toString(),
   *         value: (item) => item * item);
   *
   *     map['1'] + map['2']; // 1 + 4
   *     map['3'] - map['2']; // 9 - 4
   *
   * If no values are specified for [key] and [value] the default is the
   * identity function.
   *
   * In the following example, the keys and corresponding values of `map`
   * are `list` values:
   *
   *     map = new Map.fromIterable(list);
   *     map[1] + map[2]; // 1 + 2
   *     map[3] - map[2]; // 3 - 2
   *
   * The keys computed by the source [iterable] do not need to be unique. The
   * last occurrence of a key will simply overwrite any previous value.
   */
  factory Map.fromIterable(Iterable iterable,
      {K key(element)?, V value(element)?}) = LinkedHashMap<K, V>.fromIterable;

  /**
   * factory Map.fromIterables(Iterable<K> keys, Iterable<V> values) =
      LinkedHashMap<K, V>.fromIterables;

      创建关联被传入的key-value的map实例。

      被创建的map是一个[LinkedHashMap].
      
      `LinkedHashMap`需要key实现兼容的==与`hashcode`, 它还允许null做为key值。
      它根据key的插入顺序进行迭代。

      这个构造器度迭代 keys和values，以及maps中的 [keys]中的每一个元素以及相关联的[values]
      中的每一个元素。
   * 
   *     List<String> letters = ['b', 'c'];
   *     List<String> words = ['bad', 'cat'];
   *     Map<String, String> map = new Map.fromIterables(letters, words);
   *     map['b'] + map['c'];  // badcat
   * 
   *  如果[keys]包含同样的对象多次， 最后出现的将会覆盖之前的值。
   *  
   *  这两个Iterable必须有相同的长度。
   * 
   * 
   * Creates a Map instance associating the given [keys] to [values].
   *
   * The created map is a [LinkedHashMap].
   * A `LinkedHashMap` requires the keys to implement compatible
   * `operator==` and `hashCode`, and it allows null as a key.
   * It iterates in key insertion order.
   *
   * This constructor iterates over [keys] and [values] and maps each element of
   * [keys] to the corresponding element of [values].
   *
   *     List<String> letters = ['b', 'c'];
   *     List<String> words = ['bad', 'cat'];
   *     Map<String, String> map = new Map.fromIterables(letters, words);
   *     map['b'] + map['c'];  // badcat
   *
   * If [keys] contains the same object multiple times, the last occurrence
   * overwrites the previous value.
   *
   * The two [Iterable]s must have the same length.
   */
  factory Map.fromIterables(Iterable<K> keys, Iterable<V> values) =
      LinkedHashMap<K, V>.fromIterables;

  /**
   *  static Map<K2, V2> castFrom<K, V, K2, V2>(Map<K, V> source) =>
      CastMap<K, V, K2, V2>(source);
   *    
   *  适配[source] 的数据源, 转换成一个 `Map<K2, V2>`类型。
   *  
   *  每一次这个集合将会生成一个key或者value，但是不是[K2]类型，或者[V2]类型，这次访问将会
   * 抛出异常。 
   * 
   *  每一次[k2]类型的key， 或者[v2]类型的value将试图添加进一个适配的map中，这个存储将会
   * 抛出异常，除非key也是[k]的实例，value也是[V]的实例。
   * 
   * 如果source数据源的所有已访问的入口有[k2]类型的key和[v2]类型的value， 并且如果所有被添加到返回map的
   * entries有[K]类型的key，[v]类型的values，那么这个返回的map将会作为 `mAP<K2, V2>`类型。
   * 
   * 
   * Adapts [source] to be a `Map<K2, V2>`.
   *
   * Any time the set would produce a key or value that is not a [K2] or [V2],
   * the access will throw.
   *
   * Any time [K2] key or [V2] value is attempted added into the adapted map,
   * the store will throw unless the key is also an instance of [K] and
   * the value is also an instance of [V].
   *
   * If all accessed entries of [source] are have [K2] keys and [V2] values
   * and if all entries added to the returned map have [K] keys and [V]] values,
   * then the returned map can be used as a `Map<K2, V2>`.
   */
  static Map<K2, V2> castFrom<K, V, K2, V2>(Map<K, V> source) =>
      CastMap<K, V, K2, V2>(source);

  /**
   * factory Map.fromEntries(Iterable<MapEntry<K, V>> entries) =>
      <K, V>{}..addEntries(entries);
   * 
   * 创建一个新的map，增加所有的entries。
   * 
   * 所有的entries按照迭代顺序被全部添加，并返回一个新的`Map<key, value>`类型的Map。
   * 
   * 如果多个[entires]有很多相同的key， 后面出现的覆盖更早出现的。
   * 
   * 
   * Creates a new map and adds all entries.
   *
   * Returns a new `Map<K, V>` where all entries of [entries]
   * have been added in iteration order.
   *
   * If multiple [entries] have the same key,
   * later occurrences overwrite the earlier ones.
   */
  factory Map.fromEntries(Iterable<MapEntry<K, V>> entries) =>
      <K, V>{}..addEntries(entries);

  /**
   * Map<RK, RV> cast<RK, RV>();
   * 如果需要，提供一个有[RK]的key，[RV]实例的map的视图，
   * 如果这个map已经是 `Map<RK, RV>`类型，那么它不做任何转换。
   * 
   * 如果这个集合包含仅仅 [RK] 类型的keys，[RV]类型的values，所有读取操作将会正确工作。
   * 如果任何操作显示是非 [RK] 类型的key， 非 [RV] 类型的value， 这个操作将会抛出异常。
   * 
   * 添加进入到map中的 entries， 对于`Map<K, V>`和`Map<RK, RV>`类型 必须是有效的，
   * 
   * 
   * Provides a view of this map as having [RK] keys and [RV] instances,
   * if necessary.
   *
   * If this map is already a `Map<RK, RV>`, it is returned unchanged.
   *
   * If this set contains only keys of type [RK] and values of type [RV],
   * all read operations will work correctly.
   * If any operation exposes a non-[RK] key or non-[RV] value,
   * the operation will throw instead.
   *
   * Entries added to the map must be valid for both a `Map<K, V>` and a
   * `Map<RK, RV>`.
   */
  Map<RK, RV> cast<RK, RV>();

  /**
   * bool containsValue(Object? value);
   * 
   * 如果map包含某个value值，那么返回true，否则返回false。
   * 如果在map中的任何values，通过==操作，等于传入的value，那么就返回true；否则返回false。
   * 
   * 
   * Returns true if this map contains the given [value].
   *
   * Returns true if any of the values in the map are equal to `value`
   * according to the `==` operator.
   */
  bool containsValue(Object? value);

  /**
   * bool containsKey(Object? key);
   * 
   * 如果这个map包含被传入的key，那么返回true；否则返回false；
   * 如果在map中的key，通过使用等号==，等于传入的key，那么就返回true，否则返回false。
   * 
   * 
   * Returns true if this map contains the given [key].
   *
   * Returns true if any of the keys in the map are equal to `key`
   * according to the equality used by the map.
   */
  bool containsKey(Object? key);

  /**
   * V? operator [](Object? key);
   * 根据参数key，返回对应的value； 如果key不在map中，则返回null。
   * 
   * 一些map允许null作为value值。
   * 对于这些maps，使用 这个操作的查表不能区分一个key是否在map中和key是对应value的值为null。
  *  如果区分很重要，那么像[containsKey]或者[putIfAbsent]方法能够被用来做判断。
   * 
   * 
   * Returns the value for the given [key] or null if [key] is not in the map.
   *
   * Some maps allow keys to have `null` as a value.
   * For those maps, a lookup using this operator cannot distinguish between a
   * key not being in the map and the key having a `null` value.
   * Methods like [containsKey] or [putIfAbsent] can be used if the distinction
   * is important.
   */
  V? operator [](Object? key);

  /**
   * void operator []=(K key, V value);
   * 
   * 根据传入的参数，获取key相关联的value。
   * 如果key已经在map中，它关联的value发生变化（即覆盖原来的vlaue值),
   * 否则key-value对将被添加到map中。 
   * 
   * Associates the [key] with the given [value].
   *
   * If the key was already in the map, its associated value is changed.
   * Otherwise the key/value pair is added to the map.
   */
  void operator []=(K key, V value);

  /**
   *  Iterable<MapEntry<K, V>> get entries;
   *  获取这个map的所有entries对象，每个entries对象包含有key-value; 
   * 
   * The map entries of [this].
   */
  Iterable<MapEntry<K, V>> get entries;

  /**
   * Map<K2, V2> map<K2, V2>(MapEntry<K2, V2> f(K key, V value));
   * 这个map的所有entries通过传入的[f]函数进行转换。
   * 
   * Returns a new map where all entries of this map are transformed by
   * the given [f] function.
   */
  Map<K2, V2> map<K2, V2>(MapEntry<K2, V2> f(K key, V value));

  /**
   * void addEntries(Iterable<MapEntry<K, V>> newEntries);
   * 增加entries的所有key-value对 到 map中。
   * 如果entries的key已经在这个map中，对应的value会被覆盖。
   * 
   * 对于iterable中的每一个[MapEntry],通过`this[entry.key] = entry.value`来判断是否相等。
   * 
   * 
   * Adds all key/value pairs of [newEntries] to this map.
   *
   * If a key of [newEntries] is already in this map,
   * the corresponding value is overwritten.
   *
   * The operation is equivalent to doing `this[entry.key] = entry.value`
   * for each [MapEntry] of the iterable.
   */
  void addEntries(Iterable<MapEntry<K, V>> newEntries);

  /**
   * V update(K key, V update(V value), {V ifAbsent()?});
   * 
   * 根据提供的key更新value, 并且返回这个key对应的新value值。
   * 如果key是存在的，唤起当前值的[update]，并且更新新的value到这个map中。
   *  
   * 如果key不存在，并且[ifAbsent]方法被提供， 调用[ifAbsent]方法，增加key和要返回的
   * value到map中。
   * 
   * 如果key不存在，且[ifAbsend]也没有提供，那么就会报错。
   * 
   * 
   * 
   * Updates the value for the provided [key].
   *
   * Returns the new value of the key.
   *
   * If the key is present, invokes [update] with the current value and stores
   * the new value in the map.
   *
   * If the key is not present and [ifAbsent] is provided, calls [ifAbsent]
   * and adds the key with the returned value to the map.
   *
   * It's an error if the key is not present and [ifAbsent] is not provided.
   */
  V update(K key, V update(V value), {V ifAbsent()?});

  /**
   * void updateAll(V update(K key, V value));
   * 
   * 更新所有的values。
   * 迭代map中的所有的entries， 并且使用 唤起[update]方法的结果来更改 value。
   * 
   * Updates all values.
   *
   * Iterates over all entries in the map and updates them with the result
   * of invoking [update].
   */
  void updateAll(V update(K key, V value));

  /**
   * void removeWhere(bool predicate(K key, V value));
   * 移除满足[predicate]的所有entries。
   * 
   * 
   * Removes all entries of this map that satisfy the given [predicate].
   */
  void removeWhere(bool predicate(K key, V value));

  /**
   * V putIfAbsent(K key, V ifAbsent());
   * 查找一个可以的value值，
   * 
   * 如果存在一个与key关联的value值，就返回value.
   * 否则调用[ifAbsent] 去获取一个新的value值，将[key]与新的这个value进行关联，然后
   * 返回新的value。

   *     Map<String, int> scores = {'Bob': 36};
   *     for (var key in ['Bob', 'Rohan', 'Sophena']) {
   *       scores.putIfAbsent(key, () => key.length);
   *     }
   *     scores['Bob'];      // 36
   *     scores['Rohan'];    //  5
   *     scores['Sophena'];  //  7
   * 调用[ifAbsent]时， 这个map此时必须没有增加或者删除key的操作。
   * 
   * 
   * Look up the value of [key], or add a new value if it isn't there.
   *
   * Returns the value associated to [key], if there is one.
   * Otherwise calls [ifAbsent] to get a new value, associates [key] to
   * that value, and then returns the new value.
   *
   *     Map<String, int> scores = {'Bob': 36};
   *     for (var key in ['Bob', 'Rohan', 'Sophena']) {
   *       scores.putIfAbsent(key, () => key.length);
   *     }
   *     scores['Bob'];      // 36
   *     scores['Rohan'];    //  5
   *     scores['Sophena'];  //  7
   *
   * Calling [ifAbsent] must not add or remove keys from the map.
   */
  V putIfAbsent(K key, V ifAbsent());

  /**
   * void addAll(Map<K, V> other);
   * 
   * 从other map中增加所有的key-value键值对到这个map中。
   * 如果other map的一个key在这个map中了，它的值会覆盖。
   * 
   * 对于other map中的每个key，以及关联的value， 相等性操作是通过 `this[key] = value`
   * 判断。递归other map， 因此在迭代期间不能发生增加删除修改等改变。
   * 
   * 
   * Adds all key/value pairs of [other] to this map.
   *
   * If a key of [other] is already in this map, its value is overwritten.
   *
   * The operation is equivalent to doing `this[key] = value` for each key
   * and associated value in other. It iterates over [other], which must
   * therefore not change during the iteration.
   */
  void addAll(Map<K, V> other);

  /**
   * V? remove(Object? key);
   * 
   * 如果key存在，那么map中删除key关联的value。 
   * 
   * 如果value被移除，那么就返回这个key对应的value。
   * 如果可以不在这个map中，返回null。
   * 
   * 注意： value可以是null值，返回null值不总是代表这个key不存在。
   * 
   * 
   * 
   * Removes [key] and its associated value, if present, from the map.
   *
   * Returns the value associated with `key` before it was removed.
   * Returns `null` if `key` was not in the map.
   *
   * Note that values can be `null` and a returned `null` value doesn't
   * always mean that the key was absent.
   */
  V? remove(Object? key);

  /**
   * void clear();
   * 移除这个map中的所有key-value键值对。
   * clear()操作之后，这个map会是一个空的。
   * 
   * Removes all pairs from the map.
   *
   * After this, the map is empty.
   */
  void clear();

  /**
   * void forEach(void f(K key, V value));
   * 
   * 为这个map中的每一对key-value键值对申请[f]函数。
   * 调用[f]方法，在方法中不能从这个map中不能增加，删除key。
   * 
   * Applies [f] to each key/value pair of the map.
   *
   * Calling `f` must not add or remove keys from the map.
   */
  void forEach(void f(K key, V value));

  /**
   * Iterable<K> get keys;
   * 从这个map中获取Iterable对象。
   * 
   * 返回的Iterable对象有高效的`length`和`contains`操作，基于这个map的[length]和[containsKey]方法。
   * 
   * 迭代的顺序根据独自的`Map`实现而定义，但是在map中的改变必须保持一致性。
   * 
   * 当迭代keys时修改map，那么会中断这次迭代。
   * 
   * 
   * The keys of [this].
   *
   * The returned iterable has efficient `length` and `contains` operations,
   * based on [length] and [containsKey] of the map.
   *
   * The order of iteration is defined by the individual `Map` implementation,
   * but must be consistent between changes to the map.
   *
   * Modifying the map while iterating the keys
   * may break the iteration.
   */
  Iterable<K> get keys;

  /**
   * Iterable<V> get values;
   * 
   * 获取这个Map的value列表。
   * 
   * 这个values根据相关联的keys的顺序进行迭代。
   * 这意味着并行的迭代[keys]和[values]将会提供成对的key-value.
   * 
   * 返回的Iterable对象，具有高效的`length`方法，基于map的`length`方法。
   * 它的[Iterable.contains]方法是基于`==`比较的。
   * 
   * 当迭代vlaue时，如果修改这个map，迭代将会被中断。
   * 
   * 
   * The values of [this].
   *
   * The values are iterated in the order of their corresponding keys.
   * This means that iterating [keys] and [values] in parallel will
   * provide matching pairs of keys and values.
   *
   * The returned iterable has an efficient `length` method based on the
   * [length] of the map. Its [Iterable.contains] method is based on
   * `==` comparison.
   *
   * Modifying the map while iterating the
   * values may break the iteration.
   */
  Iterable<V> get values;

  /**
   * int get length;
   * 获取这个map中key-value键值对的数量。
   * 
   * The number of key/value pairs in the map.
   */
  int get length;

  /**
   * 
   * 如果map中没有一对key-value，那么返回true，否则返回false。
   * Returns true if there is no key/value pair in the map.
   */
  bool get isEmpty;

  /**
   * bool get isNotEmpty;
   * map中至少有一对key-value, 那么返回true，否则返回false。
   * 
   * Returns true if there is at least one key/value pair in the map.
   */
  bool get isNotEmpty;
}

/**
 * MapEntry<K, V>
 * 在Map中，使用key-value键值对代表一个entry。
 * 
 * 
 * A key/value pair representing an entry in a [Map].
 */
class MapEntry<K, V> {
  /** The key of the entry. */
  final K key;

  /** The value associated to [key] in the map. */
  final V value;

  /** Creates an entry with [key] and [value]. */
  const factory MapEntry(K key, V value) = MapEntry<K, V>._;

  const MapEntry._(this.key, this.value);

  String toString() => "MapEntry(${key.toString()}: ${value.toString()})";
}

```





# 第七篇 函数定义与形参，箭头函数，匿名函数，闭包



# 第八篇 类与对象



# 第九篇 类， 静态成员，操作符，继承



# 第十篇  抽象类，接口，多态



# 第十一篇 类实现多个接口，以及mixins



# 第十二篇 泛型，泛型方法，泛型类，泛型接口



# 第十三篇 库，自定义库，系统库，第三方库









