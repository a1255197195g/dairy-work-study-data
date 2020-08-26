# 一 dart语言之旅

​    在假定你已经知道怎么用其它语言去编程的情况下，这一页展示你怎么使用每一个主要的dart特性，从变量，操作到类和库。对于喜欢精简的人，对于这么语言不太完整的介绍，请看`language samples page`.

​    学习更多关于dart核心库，请参考 `library tour`. 无论何时你想要更多关于语言特性的详情，请查阅 ·dart language specifcation·

<table>
    <tr>
    	<td bgColor="#E7F8FF" height=100>
注意：使用dartPad，你能够体验大多数dart的语言特性。`Open DartPad` <br> <br>
这一页使用嵌入式的 dartPads 去展示一些案例。如果你看见空的盒子，而不是 dartPads, 去访问`dartPad troubleshooting page`
        </td>
    </tr>
</table>



## 一个基本的dart编程

接下来的代码使用了许多dart最基础的特性：

```
//定义一个函数
printInteger( int aNumber ){
	print('The number is $aNumber'); //去控制台打印。
}

//这是app开始执行的地方
main(){
	var number = 42; //声明并且初始化一个变量。
	printInteger(number); //调用一个函数。
}
```

在这里的这个程序所使用的特希那个，应用于所有或者几乎所有的dart应用。

<font color="green">// 这是一个注释.</font>

一个单行注释。dart也支持多行注释和文档注释。关于细节，请参考 `Comments`

<font color="green">int</font>

一种类型。一些其他的内建类型是 `String`, `List`, 和 `bool`.

<font color="green">42</font>

一个数字字面量。数字字面量是一种编译期间常量。

<font color="green">print()</font>

展示输出的一种便利方式。

<font color="green">`...` (或者 "...")</font>

一个字符串字面量。

<font color="green">$variableName(或者${expression})</font>

字符串插补：在一个字符串字面量的内部，包含一个变量或者表达式字符串的等价物。关于更多信息，请参考`Strings`.

<font color="green">main()</font>

这个特殊的，必须的，顶级函数，是应用执行开始的地方。关于更多信息，请参考`The main() function`.

<font color="green">var</font>

一种声明变量而又不虚指定变量类型的方式。



<table>
    <tr>
    	<td bgColor="#E7F8FF" height=80>
注意： 这个位置的代码遵循在 `Dart style guide` 中的规定。
        </td>
    </tr>
</table>



## 重要概念

当你学习关于dart语言时，保持这些事实和概念在脑中。

- 你能放置变量中的任何东西都是一个对象，并且任何对象都是一个类的实例。即使数组，函数，和 null 都是对象。所有对象继承自`Object`类。
- 尽管dart是强类型的，但是类型注解是可选择的，，因为dart能推断类型。在上面的代码中，数字42是被推导成为int类型。当你想显示的说没有类型是可期待的，使用这种特殊的类型`dynamic`.
- dart支持 `类` 这种类型，像`List<int>一种integer类型的列表，或者List<dynamic>(一种任意类型对象的集合)。`
- dart支持顶级函数（比如main()）, 而且函数绑定到一个类或者对象中（分别有静态方法和实例方法）。

- 类似地，dart支持顶级变量，并且变量也可以绑定到一个类或者对象中（静态变量或者实例变量）。实例变量有时候叫做`fields`或者`properties`.
- 不像java，dart没有关键字`public`, `protected`,和`private`.如果一个标识符以下划线(_)开始，对于它的库而言，它是私有的。关于详情，请查看`Libraries and visibility`.
- 标识符可以以字符或者下划线(_)，随后是任何字符加数字的组合。
- dart有表达式（在运行时有值）和声明（在运行时没有值）。比如。条件表达式 condition ? expr1 ： expr2，有一个expr1或者expr2的值。对于表达式而言， if-else的statement是没有值的。一个statement经常包含一个或者多个表达式，但是一个表达式不能直接包含一个statement。
- dart工具能够报告两种问题：警告或者错误。警告仅仅是一种指示，你的代码可能不能工作，但是他们不会阻断你的程序执行。错误可能是编译期间或者运行期间。一个编译期错误将代码从运行中完全阻断。在代码执行时，一个运行时错误会导致一个异常的抛出。

## 关键字

下面的表格列举了dart语言特殊处理的单词。

| <font color="green">abstract</font><sup>2</sup>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | <font color="green">else</font>                  | <font color="green">import</font><sup>2</sup>    | <font color="green">super</font>              |
| ------------------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ | --------------------------------------------- |
| <font color="green">as</font><sup>2</sup>                    | <font color="green">enum</font>                  | <font color="green">in</font>                    | <font color="green">switch</font>             |
| <font color="green">assert</font>                            | <font color="green">export</font><sup>2</sup>    | <font color="green">interface</font><sup>2</sup> | <font color="green">sync</font><sup>1</sup>   |
| <font color="green">async</font><sup>1</sup>                 | <font color="green">extends</font>               | <font color="green">is</font>                    | <font color="green">this</font>               |
| <font color="green">await</font><sup>3</sup>                 | <font color="green">extension</font><sup>2</sup> | <font color="green">library</font><sup>2</sup>   | <font color="green">throw</font>              |
| <font color="green">break</font>                             | <font color="green">external</font><sup>2</sup>  | <font color="green">mixin</font><sup>2</sup>     | <font color="green">true</font>               |
| <font color="green">case</font>                              | <font color="green">factory</font><sup>2</sup>   | <font color="green">new</font>                   | <font color="green">try</font>                |
| <font color="green">catch</font>                             | <font color="green">false</font>                 | <font color="green">null</font>                  | <font color="green">typeof</font><sup>2</sup> |
| <font color="green">class</font>                             | <font color="green">final</font>                 | <font color="green">on</font><sup>1</sup>        | <font color="green">var</font>                |
| <font color="green">const</font>                             | <font color="green">finally</font>               | <font color="green">operator</font><sup>2</sup>  | <font color="green">void</font>               |
| <font color="green">continue</font>                          | <font color="green">for</font>                   | <font color="green">part</font><sup>2</sup>      | <font color="green">while</font>              |
| <font color="green">covarian</font><sup>2</sup>              | <font color="green">Function</font><sup>2</sup>  | <font color="green">rethrow</font>               | <font color="green">with</font>               |
| <font color="green">default</font>                           | <font color="green">get</font><sup>2</sup>       | <font color="green">return</font>                | <font color="green">yield</font><sup>3</sup>  |
| <font color="green">deferred</font><sup>2</sup>              | <font color="green">hide</font><sup>1</sup>      | <font color="green">set</font><sup>2             |                                               |
| <font color="green">do</font>                                | <font color="green">if</font>                    | <font color="green">show</font><sup>1</sup>      |                                               |
| <font color="green">dynamic</font><sup>2</sup>               | <font color="green">implement</font><sup>2</sup> | <font color="green">static</font><sup>2</sup>    |                                               |

避免使用这些关键字作为标识符。然后，如果必须，这些有上标的被标记的关键字能够作为关键字。

- 有上标 <font color="green">1</font> 的单词是上下文关系的关键字，它仅仅在特殊的地方有含义。他们在任何地方都是有效的标识符。
- 有上标 <font color="green">2</font> 的单词是内建的关键字，用于简化javascript代码转换成dart的任务，这些关键字在大多数地方都是有效的标识符，但是他们不能被用于作为类或者类型的名字，或者作为重要的前缀。
- 有上标 <font color="green">3</font> 是新加入的关键字，在dart1.0发布版之后被添加，与异步支持有关的有限个保留字。你不能在被 `async`, `async*`, 或者`sync*` 标记的函数体内 使用 `await` 或者 `yield` 作为一个标识符。





## 变量

这里有一个创建变量并且初始化它的案例。

```
var name = 'Bob';
```

变量存储引用。被调用名字的变量包含一个值为 Bob的字符串对象的引用。

这个有名字的变量类型被推断为`String`，但是你可以通过指定类型来改变这个类型。如果一个对象不被限制为一种类型，可以指定为`Object`或者`dynamic`类型, 遵循`design guidelines`.

```
dynamic name = 'Bob';
```

另一个选择是去显示地声明可以被推断的类型。

```
String name = 'Bob';
```

<table>
    <tr>
    	<td bgColor="#E7F8FF" height=80>
注意： 这一页是本地变量遵循样式指南建议的变量使用，而不是类型注解。
        </td>
    </tr>
</table>



### 默认值

没有初始化的变量又一个null类型的初始化值。即使变量是一个数字类型也初始化为null。因为数字如同在dart中的任何东西，都是对象。

```
int lineCount;
assert(lineCount == null);
```

<table>
    <tr>
    	<td bgColor=#E7F8FF height=100>
注意：生产环境的code忽略assert()函数的调用。另一方面，在开发阶段，如果条件为false，assert(condition)会抛出一个异常。关于详情，请查看<font color='green'>Assert</font>         
        </td>
    </tr>
</table>



### 常量final和const

## 内建类型

### 数字类型 Numbers

### 字符串类型 Strings

### 布尔类型 Booleans

### 列表类型 Lists

### 集合类型 Sets

### 字典类型 Maps

### Runes and grapheme clusters

### Symbols