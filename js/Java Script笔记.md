# Java Script

### java script 是什么？

java script是一种运行在客户端的脚本语言（script是脚本的意思）

脚本语言：不需要编译，运行过程中由js解释器（js引擎）**逐行**来进行解释并执行



### ECMAscript

ECMAscript 规定了 js 的编程语法和基础核心知识，是所有浏览器厂商共同遵守的一套 js 语法工业标准



### js的三种书写位置

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <!-- 2.内嵌式的js -->
    <!-- <script>
      alert("唐伯虎点秋香");
    </script> -->
    <!-- 3.外部式的js，注意script是双标签 -->
    <script src="yi.js"></script>
  </head>
  <body>
    <!-- 1.行内的js直接写在元素内部 -->
    <input type="button" value="唐伯虎" onclick="alert('秋香姐')" />
  </body>
</html>

```

##### 1.行内式js

可以将单行或少量JS 代码写在HTML标签的事件属性中（以on 开头的属性），如：onclick
注意单双引号的使用：在HTML中我们推荐使用双引号,JS中我们推荐使用**单引号**
可读性差，在html中编写JS大量代码时，不方便阅读；
引号易错，引号多层嵌套匹配时，非常容易弄混；
特殊情况下使用

##### 2.内嵌js

可以将多行JS代码写到script标签中
内嵌 JS 是学习时常用的方式

##### 3.外部js文件

利于HTML页面代码结构化，把大段JS代码独立到HTML页面之外，既美观，也方便文件级别的复用
引用外部JS文件的 script 标签中间不可以写代码

```html
 <script src="yi.js">这里不能写代码哦</script>
```

适合于JS代码量比较大的情况



##### js的注释

```html
<script>
    // 1．单行注释 ctrl + /
/* 2．多行注释 默认的快捷键 shift + alt+ a
   2．多行注释 */
</script>

```



##### js 的输入输出语句

方法							        说明
alert(msg）			   		浏览器弹出警示框
console.log(msg)	  		浏览器控制台打印输出信息
prompt(info)			  		浏览器弹出输入框，用户可以输入

```html
<script>
// 这是一个输入框
prompt('请输入您的年龄');
// alert 弹出警示框 输出的 展示给用户的
alert('计算的结果是');
// console 控制台输出 给程序员测试用的
console.log('我是程序员能看到的');
</script>
```



##### 什么是变量？

白话：变量就是一个装东西的盒子。
通俗：变量是用于存放数据的容器。我们通过变量名获取数据，甚至数据可以修改。

###### 变量在内存中的存储

本质：变量是程序在内存中申请的一块用来存放数据的空间。
类似我们酒店的房间，一个房间就可以看做是一个变量。



##### 变量的使用

###### 声明

```html
声明变量
var age;// 声明一个名称为age的变量
var 是一个JS关键字，用来声明变量(variable是变量的意思）。使用该关键字声明变量后，计算机会自动为变量分配内存空间，不需要程序员管
age 是程序员定义的变量名，我们要通过变量名来访问内存中分配的空间


```



###### 赋值

```html
age = 10;
//给age这个变量赋值为10
 = 用来把右边的值赋给左边的变量空间中 此处代表赋值的意思
 变量值是程序员保存到变量空间里的值

```

例：

```html
<script>
// 1．声明了一个age的变量
var age;
// 2.赋值    把值存入这个变量中
age =18;
// 3.输出结果
console.log(age);
</script>
```



###### 变量的初始化

```html
var age=18;//声明变量同时赋值为18
```

声明一个变量并赋值，我们称之为变量的初始化.



##### 变量语法扩展

###### 1.更新变量

一个变量被重新复赋值后，它原有的值就会被覆盖，变量值将以最后一次赋的值为准。

```html
var age = 18;
age = 81;
//最后的结果就是81因为18被覆盖掉了
```

###### 2.同时声明多个变量

同时声明多个变量时，只需要写一个var，多个变量名之间使用英文逗号隔开。

```html
var age= 10, name = 'zs',sex = 2;
```

###### 3.声明变量的特殊情况

```html
// 只声明不赋值 结果是？   程序也不知道里面存的是啥，所以结果是undefined 未定义的
var sex;
console.log(sex)；// undefined
// 3.2 不声明 不赋值 直接使用某个变量会报错滴
// console.log(tel);
// 3.3 不声明直接赋值使用,不会报错但平常不推荐使用
qq = 110;
console.log(qq);

```



##### 变量命名规范

由字母(A-Za-z)、数字(0-9)、下划线( _ )、美元符号($)组成，如：usrAge,num01,_name
严格区分大小写。var app;和 var App;是两个变量
不能以数字开头。18age 是错误的
不能 是关键字、保留字。例如：var、for、while （有的浏览器中name也有特殊含义，我们尽量不适用它作变量名）
变量名必须有意义。不要使用拼音简写：MMD  BBD nl
遵守驼峰命名法。首字母小写，后面单词的首字母需要大写。 myFirstName
推荐翻译网站：有道 爱词霸



### 数据类型

JavaScript 是一种弱类型或者说动态语言。这意味着不用提前声明变量的类型，在程序运行过程中，类型会
被自动确定。

###### typeof

我们可以用：typeof 来检测我们的数据类型

```
var num = 10;
console.log(typeof num);//number
van str ="pink";
console.log(typeof str)；// string
var flag = true;
console.log(typeof flag)；//boolean
var vari := undefined;
console.log(typeof vari)；//undefined
var timer = null;
console.log(typeof timer)；// object
//prompt取过来的值是字符型的
var age=prompt(‘请输入您的年龄');
console.log(age);
console.log(typeof age);
```

**注意：prompt取过来的值是字符型的**



简单数据类型（基本数据类型）
JavaScript中的简单数据类型及其说明如下：

简单数据类型				说明																				      			 	默认值

------

Number						数字型，包含 整型值和浮点型值，如 21、0.21								0
Boolean						布尔值类型，如true 、false，等价于1和0										false
String							字符串类型，如“张三” 注意咱们js 里面，字符串都带引号				“”
Undefined					var a;声明了变量 a 但是没有给值，此时 a = undefined				  undefined
Null								var a = null; 声明了变量 a 为空值														nul

------

##### 数字型：NumberJavaScript

数字类型既可以用来保存整数值，也可以保存小数(浮点数）。

数字型进制

```
最常见的进制有二进制、八进制、十进制、十六进制。
//1.八进制数字序列范围：0~7
var num1 = 07;
// 对应十进制的7
var num2 = 019;
// 对应十进制的19
var num3 =08;
// 对应十进制的8
//2.十六进制数字序列范围：0～9以及A～F
var num = 0xA;
现阶段我们只需要记住，在js中，八进制前面加0，十六进制前面加 Ox

 数字型范围
JavaScript中数值的最大和最小值
alert(Number.MAX_VALUE); // 1.7976931348623157e+308
alert(Number.MIN_VALUE); // 5e-324

 数字型三个特殊值
alert(Infinity);//Infinity	   

alert(-Infinity)；// -Infinity

alert(NaN) ;//NaN

 Infinity ,代表无穷大，大于任何数值
-Infinity,代表无穷小，小于任何数值
NaN ， Not a number 代表一个非数值
```



#####  isNaN( )

用来判断一个变量是否为非数字的类型，返回true 或者 false



### 字符串型String

字符串型可以是引号中的任意文本，其语法为双引号""和 单引号"

```
var strMsg ="我爱北京天安门~"；// 使用双引号表示字符串

var strMsg2 = '我爱吃猪蹄～' ;// 使用单引号表示字符串

// 常见错误
var strMsg3 = 我爱大肘子；// 报错，没使用引号，会被认为是js代码，但js没有这些语法
因为 HTML标签里面的属性使用的是双引号，JS 这里我们更推荐使用单引号
```



##### 字符串引号嵌套

```
JS可以用单引号嵌套双引号，或者用双引号嵌套单引号（外双内单，外单内双）

var strMsg = '我是"高帅富"程序猿’；// 可以用''包含"" 
var strMsg2 - "我是'高帅富'程序猿"； // 也可以用""包''
// 常见错误
var badQuotes = 'What on earth2"；// 报错，不能单双引号搭配

```



###### 字符串转义符

```
类似HTML里面的特殊字符，字符串中也有特殊字符，我们称之为转义符。
转义符都是\开头的，常用的转义符及其说明如下：
转义符			解释说明
\n			  换行符，n 是 newline 的意思
\\			  斜杠\
\'		      单引号
\"		      双引号
\t            tab缩进
\b			  空格 , b 是 blank 的意思
```



##### 字符串长度

字符串是由若干字符组成的，这些字符的数量就是字符串的长度。通过字符串的 length 属性可以获取整个字符
串的长度。

```
var strMsg ="我是帅气多金的程序猿！";
alert(strMsg.length);// 显示11
```



##### 字符串拼接

多个字符串之间可以使用＋进行拼接，其拼接方式为字符串＋任何类型=拼接之后的新字符串
拼接前会把与字符串相加的任何类型转成字符串，再拼接成一个新的字符串

```
//1.1 字符串“相加”
alert('hello' + ' ' + 'world')；//
hello world
//1.2 数值字符串“相加”
alert('100' + '100') : // 100100
//1.3 数值字符串＋数值
alert('11' + 12);	// 1112


```



##### Undefined和Null

```
一个声明后没有被赋值的变量会有一个默认值undefined（如果进行相连或者相加时，注意结果）
var variable;
console.log(variable);//undefined
console.log('你好' + variable);// 你好undefined
console.log(11 + variable);//NaN
console.log(true + variable);// NaN
个声明变量给null值，里面存的值为空（学习对象时，我们继续研究null)
var vari = null;
console.log('你好'+ vari)： // 你好null
console.log(11 + vari);// 11
console.log(true + vari);//1


```



######  字面量

字面量是在源代码中一个固定值的表示法，通俗来说，就是字面量表示如何表达这个值。
数字字面量：8,9,10
字符串字面量：'黑马程序员，大前端"。
布尔字面量：true , false



##### 数据类型转换

方式													说明											案例

------

变量.toString()								转成字符串								var num=1; alert(num.toString());
String(变量) 强制转换					转成字符串								var num = 1; alert(String(num));
**加号拼接字符串**						和字符串拼接的结果都是字符串	var num = 1; alert(num+ "我是字符串");

------

注意：toString0和String0使用方式不一样。
三种转换方式，我们**更喜欢用第三种加号拼接字符串**转换方式，这一种方式也称之为隐式转换。



##### 转换为数字型（重点）

方式											说明													案例

------

parselnt(string) 函数			将string类型转成整数数值型			parselnt("8")						

parseFloat(string) 函数		将string类型转成浮点数数值型		parseFloat('78.21')
Number()强制转换函数		将string类型转换为数值型				Number('12")
js 隐式转换( - * /）					利用算术运算隐式转换为数值型		'12'-0

------

注意 parselnt和parseFloat**单词的大小写**，这2个是重点



##### 转换为布尔型

方式																		说明									案例
Boolean()函数												其他类型转成布尔值			Boolean('true‘);

------

```
代表空、否定的值会被转换为 false如"、O、NaN、null、undefined
其余值都会被转换为 true
console.log(Boolean('')) : // false
console.log(Boolean(0))；// false
console.log(Boolean(NaN)); // false
console.log(Boolean(null));// false
console.log(Boolean(undefined)); // false
console.log(Boolean('小白')); // true
console.log(Boolean(12));// true


```



#####  浮点数的精度问题

```
浮点数值的最高精度是17位小数，但在进行算术计算时其精确度远远不如整数。
var result= 0.1 + 0.2;
// 结果不是 0.3，而是：0.30000000000000004
console.log(0.07 * 100);
//结果不是 7， 而是：7.000000000000001

```



#####  递增运算符

1.前置递增运算符
**++num**
前置递增，就是自加1，类似于num = num + 1，但是 ++num 写起来更简单。
使用口诀：先自加，后返回值

后置递增运算符
**num++**
后置递增，就是自加1，类似于num = num + 1 , 但是num+＋写起来更简单。
使用口诀：先返回原值，后自加



#####  比较运算符概述

概念：比较运算符（关系运算符）是两个数据进行比较时所使用的运算符，比较运算后，会返回一个布尔值
（true/false）作为比较运算的结果。

------

运算符名称					说明										案例					结果

------

​		<							小于号									1<2					   true

​	   >						 	大于号									1>2						false
​	  >=				大于等于号(大于或者等于)			   2>=2					true
​	  <=			    小于等于号（小于或者等于）		  3<=2					false

==						判等号（会转型）				37 == 37					true
	!=						不等号									37 != 37					false

===  !==			 全等 要求值和 数据类型都一致	   37 === '37‘			   false

------



##### 逻辑运算符概述

概念：逻辑运算符是用来进行布尔伯运算的运算符，其返回值也是布尔值。后面开发中经常用于多个条件的判断

逻辑运算符					说明										案例

------

&&					"逻辑与"，简称"与" and			true && false //false
||						"逻辑或"，简称“或"or				true ll false // true
  !							"逻辑非"，简称“非”					not! true //false

------



##### 短路运算（逻辑中断）

短路运算的原理：当有多个表达式（值）时,左边的表达式值可以确定结果时,就不再继续运算右边的表达式的值;
1.逻辑与
语法：表达式1 && 表达式2
如果第一个表达式的值为真，则返回表达式2
如果第一个表达式的值为假，则返回表达式1



##### 逻辑中断（短路操作）

2.逻辑或
语法：
表达式1‖表达式2
如果第一个表达式的值为真，则返回表达式1
如果第一个表达式的值为假，则返回表达式2

```
console.log( 123 ll 456 );//123
console.log( 0 ll 456 );//456
console.log( 123 || 456||789) ;//123
```



##### 赋值运算符

```
赋值运算符					说明						案例
直接赋值				var usrName = "我是值；			=
+=、-=					加、减一个数 后在赋值			varage=10; age+=5;//15

*=、/=、%=				乘、除、取模 后在赋值			var age = 2; age*=5;//10


```



##### 三元运算符

三元运算符： 条件表达式 ?( 表达式1) : (表达式2);

条件表达式为真时返回表达式1的值，为假则返回表达式2的值。 

##### 运算符优先级

 优先级					运算符					顺序

------

​	1							小括号					 ()
​	2						一元运算符				++、-- 、!
​	3						算数运算符				先*/% 后+-
​	4						关系运算符				> >=  <  <=
​	5						相等运算符				== 、!= 、!== 、===
​	6						逻辑运算符				先&& 后 II
​	7						赋值运算符					=
​	8						逗号运算符					,

------

### 分支结构

#####  if 语句

1.语法结构
// 条件成立执行代码，否则什么也不做

```
if （条件表达式）
{
// 条件成立执行的代码语句
}

if else语句（双分支语句）
1.语法结构
//条件成立 执行 if 里面代码，否则执行else 里面的代码
if (条件表达式){
//[如果] 条件成立执行的代码
} else {
//[否则] 执行的代码
}
```





##### switch 语句

语法结构
switch 语句也是多分支语句，它用于基于不同的条件来执行不同的代码。当要针对变量设置一系列的特定值
的选项时，就可以使用 switch。

```
// 1．switch 语句也是多分支语句 也可以实现多选1
// 2．语法结构 switch 转换、开关
case 小例子或者选项的意思
switch(表达式）{
case value1:
执行语句1;
break;
case value2:
执行语句2；
break;
default:
执行最后的语句;
}

// 3．执行思路 利用我们的表达式的值 和 case 后面的选项值相匹配，如果匹配上就执行该case里面的语句 如果都没有匹配上，那么执行 default里面的语句。

注意：
// 1．我们开发中表达式我们经常写成变量
// 2．我们num 的值 和 case 里面的值相匹配的时候是" 全等" 必须是值和数据类型一致才可以
// 3．break 如果当前的case里面没有break 则不会退出switch 是继续执行下一个case
```



### 循环结构

##### for语句

```
// 1．for 重复执行某些代码，通常和计数有关系
// 2．for 语法结构
for (初始化变量；条件表达式；操作表达式）{
// 循环体
}
// 3．初始化变量 就是用var 声明的一个普通变量， 通常用于作为计数器使用
// 4. 条件表达式 就是用来决定每一次循环是否继续执行 就是终止的条件
// 5．操作表达式 是每次循环最后执行的代码 经常用于我们计数器变量进行更新（递增或者递减）
```

##### 断点调试：

断点调试是指自己在程序的某一行设置一个断点，调试时，程序运行到这一行就会停住，然后你可以一步一步往下调试，调试
过程中可以看各个变量当前的值，出错的话，调试到出错的代码行即显示错误，停下。
断点调试可以帮我们观察程序的运行过程
浏览器中按F12--> sources -->找到需要调试的文件-->在程序的某一行设置断点
Watch: 监视，通过watch可以监视变量的值的变化，非常的常用。
F11:程序单步执行，让程序一行一行的执行，这个时候，观察watch中变量的值的变化。



##### while 循环语法结构

```

// while (条件表达式) {
// 循环体
// }
// 2．执行思路
当条件表达式结果为true,则执行循环体 否则 退出循环
// 4．里面应该也有计数器 初始化变量
// 5．里面应该也有操作表达式完成计数器的更新 防止死循环

```



###### do... while 语句

do... while 语句其实是while 语句的一个变体。该循环会先执行一次代码块，然后对条件表达式进行判断，如

果条件为真，就会重复执行循环体，否则退出循环。

```
do... while 语句的语法结构如下：
do {
// 循环体代码 一 条件表达式为 true 时重复执行循环体代码
} while（条件表达式）;
执行思路：
① 先执行一次循环体代码
② 再执行条件表达式，如果结果为true，则继续执行循环体代码，如果为false，则退出循环，继续执行后面
代码

```

注意：先再执行循环体，再判断，我们会发现do...while循环语句至少会执行一次循环体代码



#####  continue 关键字

 continue 关键字用于立即跳出本次循环，继续下一次循环（本次循环体中continue之后的代码就会少执行一次）。

#####  break 关键字

break关键字用于跳出整个循环（循环结束）。



##### 标识符命名规范

变量、函数的命名必须要有意义
变量的名称一般用名词
函数的名称一般用动词



### 创建数组

##### 什么是数组呢？

答：数组是指一组数据的集合，其中的每个数据被称作元素，在数组中可以存放**任意类型**的元素。数组是
种将一组数据存储在单个变量名下的优雅方式。

##### 利用new创建数组

```
var 数组名 = new Array().
var arr = new Array();
// 创建一个新的空数组.
例如：
// var arr1 = new Array()； // 创建了一个空的数组

// var arr1 = new Array(2); // 这个2 表示 数组的长度为 2 里面有2个空的数组元素

var arr1 = new Array(2，3)；// 等价于 [2,3] 这样写表示 里面有2个数组元素 是 2和3
console.log(arr1);

```


注意Array （），A要大写。

#####  利用数组字面量创建数组

```
//1．使用数组字面量方式创建空的数组
var
数组名 = []；
//2．使用数组字面量方式创建带初始值的数组
var
数组名 = ['小白','小黑','大黄','瑞奇'];
```

数组的字面量是方括号 [ ]
声明数组并赋值称为数组的初始化
这种字面量方式也是我们以后最多使用的方式



数组的索引
索引（下标）：用来访问数组元素的序号（数组下标从0开始）。

数组可以通过索引来访问、设置、修改对应的数组元素，我们可以通过“ 数组名 [ 索引 ] ”的形式来获取数组中的
元素。
这里的访问就是获取得到的意思

```
// 定义数组
var arrStus=[1,2,3]；
// 获取数组中的第2个元素
alert(arrStus[1]);

```



##### 数组的长度

使用“数组名.length”可以访问数组元素的数量（数组长度）。



##### 通过修改 length 长度新增数组元素

可以通过修改length长度来实现数组扩容的目的
length 属性是可读写的

```
var arr = ['red', 'green', 'blue', 'pink'];
arr.length = 7;
console.log(arr);
console.log(arr[4]);
console.log(arr[5]);
console.log(arr[6]); 
```

其中索引号是4，5，6的空间没有给值，就是声明变量未给值，默认值就是 undefined。



#####  通过修改数组索引新增数组元素

可以通过修改数组索引的方式追加数组元素
不能直接给数组名赋值，否则会覆盖掉以前的数据

```
// 2．新增数组元素 修改索引号 追加数组元素
var arr1 = ['red', 'green', 'blue'];
arr1[3] = 'pink';
console.log(arr1);
arr1[4] = 'hotpink';//追加
console.log(arr1);
arr1[O] = 'yellow'；// 这里是替换原来的数组元素
console.log(arr1);
arr1 = '有点意思';
console.log(arr1);//不能直接给数组名赋值，否则里面的数组元素都没有了。

```



### 函数使用

声明函数 和 调用函数

1. ##### 声明函数

   ```
   // function 函数名(）{
   //
   // 函数体
   // }
   function sayHi(){
   console.log('hi~~');
   }
   ```

   function 是声明函数的关键字,必须小写
   由于函数一般是为了实现某个功能才定义的，所以通常我们将函数名命名为动词，比如 getSum

   函数不调用自己不执行

2. ##### 调用函数

   ```
   // 调用函数
   函数名（）；// 通过调用函数名来执行函数体代码
   ```

   调用的时候千万不要忘记添加小括号
   口诀：函数不调用，自己不执行。
   注意：声明函数本身并不会执行代码，只有调用函数时才会执行函数体代码。

##### 函数的封装

函数的封装是把一个或者多个功能通过函数的方式封装起来，对外只提供一个简单的函数接口
简单理解：封装类似于将电脑配件整合组装到机箱中（类似快递打包）



##### 形参和实参

在声明函数时，可以在函数名称后面的小括号中添加一些参数，这些参数被称为形参，而在调用该函数时，
同样也需要传递相应的参数，这些参数被称为实参。
参数							说明

------

形叁							形式上的参数 函数定义的时候 传递的参数 当前并不知道是什么
实参							实际上的参数 函数调用的时候传递的参数 实参是传递给形参的

------

参数的作用：在函数内部某些值不能固定，我们可以通过参数在调用函数时传递不同的值进去。



 函数形参和实参个数不匹配问题
参数个数										说明

------

实参个等于形参个数					输出正确结果
实参个数多于形参个数				只取到形参的个数
实参个数小于形参个数				多的形参定义为undefined，结果为NaN

------

```
function sum(num1, num2) {
console.log(num1 + num2);
}
sum（100，200）；
// 形参和实参个数相等，输出正确结果
sum
(100,400,500,700)
//实参个数多于形参，只取到形参的个数.
sum(200)；
// 实参个数少于形参，多的形参定义为undefined，结果为NaN

```



##### 函数的返回值格式

```
// function 函数名() {
//
return 需要返回的结果;
// }
// 函数名();
//（1）我们函数只是实现某种功能，最终的结果需要返回给函数的调用者函数名()通过return 实现的
//（2）只要函数遇到return 就把后面的结果 返回给函数的调用者 函数名()= return后面的结果

```



##### return

注意：return之后的语句不被执行。

​			return只能返回一个值，如果用逗号返回多个值，以最后一个值为准。

​			（可以通过返回一个数组的方式实现返回多个值的效果）

​			当函数中有return则返回return后面的值，没有return则返回undefined



##### arguments 的使用 

只有函数才有 arguments

```
function fn(){
// console.log(arguments)；// 里面存储了所有传递过来的实参arguments=[1,2,3];
// console.log(anguments.length);
// console.log(arguments[2]);
// 我们可以按照数组的方式遍历arguments
for (var i = 0; i < anguments.length; i++) {
console.log(anguments[i]);
}
}
fn(1, 2, 3);
fn(1, 2, 3, 4, 5);
```

// 伪数组 并不是真正意义上的数组
// 1．具有数组的 length 属性
// 2．按照索引的方式进行存储的
// 3．它没有真正数组的一些方法 pop(）push()等等



#####  函数的两种声明方式

```
// 1．利用函数关键字自定义函数(命名函数)
function fn() {
				fn();
			   }
// 2．函数表达式(匿名函数)
// var 变量名 =function(){};
var fun = function(aru) {
console.log("我是函数表达式");
console.log(aru);
}
fun('pink老师');
```

//（1）fun是变量名 不是函数名
//（2）函数表达式声明方式跟声明变量差不多，只不过变量里面存的是值，而函数表达式里面存的是函数。
//（3）函数表达式也可以进行传递参数

##### 箭头函数

箭头函数实例化的函数对象与正式的函数表达式创建的函数对象行为是相同的。

任何可以使用函数表达式的地方，都可以使用箭头函数。

```
let ints = [1, 2, 3];
    console.log(ints.map(function(i) { return i + 1; }));   // [2, 3, 4]
    console.log(ints.map((i) => { return i + 1 }));          // [2, 3, 4]
```

如果只有一个参数，那也可以不用括号。只有没有参数，或者多个参数的情况下，才需要使用括号：

    // 以下两种写法都有效
    let double = (x) => { return 2 ＊ x; };
    let triple = x => { return 3 ＊ x; };
    // 没有参数需要括号
    let getRandom = () => { return Math.random(); };
    // 多个参数需要括号
    let sum = (a, b) => { return a + b; };
    // 无效的写法：
    let multiply = a, b => { return a ＊ b; };

箭头函数也可以不用大括号，但这样会改变函数的行为。使用大括号就说明包含“函数体”，可以在一个函数中包含多条语句，跟常规的函数一样。如果不使用大括号，那么箭头后面就只能有一行代码，比如一个赋值操作，或者一个表达式。而且，省略大括号会隐式返回这行代码的值：

    // 以下两种写法都有效，而且返回相应的值
    let double = (x) => { return 2 ＊ x; };
    let triple = (x) => 3 ＊ x;
    // 可以赋值
    let value = {};
    let setName = (x) => x.name = "Matt";
    setName(value);
    console.log(value.name); // "Matt"
    // 无效的写法：
    let multiply = (a, b) => return a ＊ b;



如果函数是使用箭头语法定义的，那么传给函数的参数将不能使用arguments关键字访问，而只能通过定义的命名参数访问。

虽然箭头函数中没有arguments对象，但可以在包装函数中把它提供给箭头函数：

```
function foo() {
      let bar = () => {
        console.log(arguments[0]); // 5
      };
      bar();
    }
    foo(5);
```



**注意** ECMAScript中的所有参数都按值传递的。不可能按引用传递参数。如果把对象作为参数传递，那么传递的值就是这个对象的引用。即：（所有函数传值都是按值传递的，普通类型的参数直接传递变量值，引用类型则传递引用的值
 按引用传递：
简单的说按值传递 则是把变量a的值 也就是 实际变量的地址复制给arg
按引用传递的话 因为a也占有内存 则是 把a所在内存的地址复制给arg 那么arg就会指向a所在内存 可以操作a所在内存改变内存的存储内容）

```
function test（arg）{}
let a = {}
test（a）
```



箭头函数虽然语法简洁，但也有很多场合不适用。

箭头函数不能使用arguments、super和new.target，也不能用作构造函数。

此外，箭头函数也没有prototype属性。



##### 函数名

因为函数名就是指向函数的指针，所以它们跟其他包含对象指针的变量具有相同的行为。

这意味着一个函数可以有多个名称，如下所示：

```
function sum(num1, num2) {
      return num1 + num2;
    }
    console.log(sum(10, 10));           // 20
    let anotherSum = sum;
    console.log(anotherSum(10, 10));   // 20
    sum = null;
    console.log(anotherSum(10, 10));   // 20
```

注意，使用不带括号的函数名会访问函数指针，而不会执行函数。



ECMAScript 6的所有函数对象都会暴露一个只读的name属性，其中包含关于函数的信息。多数情况下，这个属性中保存的就是一个函数标识符，或者说是一个字符串化的变量名。即使函数没有名称，也会如实显示成空字符串。如果它是使用Function构造函数创建的，则会标识成"anonymous"



##### 函数参数

ECMAScript函数的参数在内部表现为一个数组。

函数被调用时总会接收一个数组，但函数并不关心这个数组中包含什么。

如果数组中什么也没有，那没问题；如果数组的元素超出了要求，那也没问题。



事实上，在使用function关键字定义（非箭头）函数时，可以在函数内部访问arguments对象，从中取得传进来的每个参数值。arguments对象是一个类数组对象（但不是Array的实例），因此可以使用中括号语法访问其中的元素（第一个参数是arguments[0]，第二个参数是arguments[1]）。而要确定传进来多少个参数，可以访问arguments.length属性。



可以通过arguments[0]取得相同的参数值。因此，把函数重写成不声明参数也可以

arguments对象可以跟命名参数一起使用，比如：

    function doAdd(num1, num2) {
      if(arguments.length===1){
        console.log(num1 + 10);
      }elseif(arguments.length===2){
        console.log(arguments[0] + num2);
      }
    }



严格模式下，arguments会有一些变化。

首先，像前面那样给arguments[1]赋值不会再影响num2的值。就算把arguments[1]设置为10, num2的值仍然还是传入的值。其次，在函数中尝试重写arguments对象会导致语法错误。（代码也不会执行。）



##### 重载

ECMAScript函数不能像传统编程那样重载。

如前所述，ECMAScript函数没有签名，因为参数是由包含零个或多个值的数组表示的。没有函数签名，自然也就没有重载。

如果在ECMAScript中定义了两个同名函数，则后定义的会覆盖先定义的。

###### 可以通过检查参数的类型和数量，然后分别执行不同的逻辑来模拟函数重载。

把函数名当成指针也有助于理解为什么ECMAScript没有函数重载

   （定义函数名字叫做a，a是一个变量指向一个存储函数的空间，如果“重载”a，相当于是把a重新赋值，赋值为另一个“重载”的函数，所以也就解释了：后面定义的会覆盖前面定义的）



##### 默认参数值

只要在函数定义中的参数后面用=就可以为参数赋一个默认值：

    function makeKing(name = 'Henry') {
      return `King ${name} VIII`;
    }
    console.log(makeKing('Louis'));   // 'King Louis VIII'
    console.log(makeKing());           // 'King Henry VIII'
给参数传undefined相当于没有传值，不过这样可以利用多个独立的默认值：

    function makeKing(name = 'Henry', numerals = 'VIII') {
      return `King ${name} ${numerals}`;
    }
    console.log(makeKing());                     // 'King Henry VIII'
    console.log(makeKing('Louis'));             // 'King Louis VIII'
    console.log(makeKing(undefined, 'VI'));   // 'King Henry VI'


在使用默认参数时，arguments对象的值不反映参数的默认值，只反映传给函数的参数。当然，跟ES5严格模式一样，修改命名参数也不会影响arguments对象，它始终以调用函数时传入的值为准：

    function makeKing(name = 'Henry') {
      name = 'Louis';
      return `King ${arguments[0]}`;
    }
    console.log(makeKing());           // 'King undefined'
    console.log(makeKing('Louis'));   // 'King Louis'



默认参数值并不限于原始值或对象类型，也可以使用调用函数返回的值

函数的默认参数只有在函数被调用时才会求值，不会在函数定义时求值。而且，计算默认值的函数只有在调用函数但未传相应参数时才会被调用。箭头函数同样也可以这样使用默认参数，只不过在只有一个参数时，就必须使用括号而不能省略了

参数初始化顺序遵循“暂时性死区”规则，即前面定义的参数不能引用后面定义的

参数也存在于自己的作用域中，它们不能引用函数体的作用域



##### 扩展操作符

对可迭代对象应用扩展操作符，并将其作为一个参数传入，可以将可迭代对象拆分，并将迭代返回的每个值单独传入。
比如，使用扩展操作符可以将前面例子中的数组像这样直接传给函数：

    console.log(getSum(...values)); // 10
因为数组的长度已知，所以在使用扩展操作符传参的时候，并不妨碍在其前面或后面再传其他的值，包括使用扩展操作符传其他参数：

    console.log(getSum(-1, ...values));             // 9
    console.log(getSum(...values, 5));              // 15
    console.log(getSum(-1, ...values, 5));         // 14
    console.log(getSum(...values, ...[5,6,7]));   // 28
对函数中的arguments对象而言，它并不知道扩展操作符的存在，而是按照调用函数时传入的参数接收每一个值



arguments对象只是消费扩展操作符的一种方式。在普通函数和箭头函数中，也可以将扩展操作符用于命名参数，当然同时也可以使用默认参数：

    function getProduct(a, b, c = 1) {
      return a ＊ b ＊ c;
    }
    let getSum = (a, b, c = 0) => {
      return a + b + c;
    }
    console.log(getProduct(...[1,2]));        // 2
    console.log(getProduct(...[1,2,3]));     // 6
    console.log(getProduct(...[1,2,3,4]));   // 6
    console.log(getSum(...[0,1]));             // 1
    console.log(getSum(...[0,1,2]));          // 3
    console.log(getSum(...[0,1,2,3]));        // 3



##### 收集参数

在构思函数定义时，可以使用扩展操作符把不同长度的独立参数组合为一个数组。这有点类似arguments对象的构造机制，只不过收集参数的结果会得到一个Array实例。

收集参数的前面如果还有命名参数，则只会收集其余的参数；如果没有则会得到空数组。因为收集参数的结果可变，所以只能把它作为最后一个参数

箭头函数虽然不支持arguments对象，但支持收集参数的定义方式，因此也可以实现与使用arguments一样的逻辑：

    let getSum = (...values) => {
      return values.reduce((x, y) => x + y, 0);
    }
    console.log(getSum(1,2,3)); // 6
另外，使用收集参数并不影响arguments对象，它仍然反映调用时传给函数的参数：

    function getSum(...values) {
      console.log(arguments.length);   // 3
      console.log(arguments);           // [1, 2, 3]
      console.log(values);               // [1, 2, 3]
    }
    console.log(getSum(1,2,3));

































### JavaScript作用域 ：

JavaScript作用域:就是代码名字（变量）在某个范围内起作用和效果，目的是为了提高程序的可靠性，重要的是减少命名冲突
// 2．js的作用域（es6）之前分为全局作用域 局部作用域
// 3．全局作用域： 整个script标签 或者是一个单独的js文件
// 4．局部作用域（函数作用域）：在函数内部就是局部作用域，这个代码的名字只在函数内部其效果和作用。



##### 全局变量

在全局作用域下声明的变量叫做全局变量(在函数外部定义的变量)
全局变量在代码的任何位置都可以使用
在全局作用域下var 声明的变量是全局变量
特殊情况下，在函数内不使用 var声明,直接赋值的变量也是全局变量（不建议使用）

#####  局部变量

在局部作用域下声明的变量叫做局部变量（在
局部变量只能在该函数内部使用
在函数内部var 声明的变量是局部变量
函数的形参实际上就是局部变量



#####  全局变量和局部变量的区别

全局变量：在任何一个地方都可以使用，只有在浏览器关闭时才会被销毁，因此比较占内存
局部变量：只在函数内部使用，当其所在的代码块被执行时，会被初始化；当代码块运行结束后，就会被
销毁，因此更节省内存空间



##### 作用域链

只要是代码，就至少有一个作用域
写在函数内部的局部作用域
如果函数中还有函数，那么在这个作用域中就又可以诞生一个作用域
根据在内部函数可以访问外部函数变量的这种机制，用链式查找（先返回上一级查找，上一级没有，则返回上上级）决定哪些数据能被内部函数访问，就称作作用域链



##### 预解析

// 1．我们js引擎运行js 分为两步：预解析 代码执行
//（1）. 预解析 js引擎会把js 里面所有的 var 还有 function 提升到当前作用域的最前面
//（2）．代码执行 按照代码书写的顺序从上往下执行
// 2．预解析分为 变量预解析（变量提升） 和 函数预解析（函数提升）
//（1）变量提升 就是把所有的变量声明提升到当前的作用域最前面 **不提升赋值操作**

```
console.log(num)；// undefined
坑 1
var num = 10;
// 相当于执行了以下代码
var num;
console.log(num);
num = 10;
```

//（2）函数提升 就是把所有的函数声明提升到当前作用域的最前面 **不调用函数**

```
fun();
var fun = function() {
console.log(22);
}
// 相当于执行了以下代码
var fun;
fun = function(){
console.log(22);
}
fun();
```

注意：函数表达式的调用必须写在函数表达式的下面。



### 对象

##### 利用字面量创建对象

对象字面量：就是花括号() 里面包含了表达这个具体事物（对象）的属性和方法。
{}里面采取键值对的形式表示
键：相当于属性名
值：相当于属性值，可以是任意类型的值（数字类型、字符串类型、布尔类型，函数类型等）。

```
var star {
name:'pink',
age :18,
sex :'男',
sayHi : function(){
alert('大家好啊~');
				  }
};

```



##### 对象的调用

对象里面的属性调用:对象,属性名，这个小点，就理解为“的“
对象里面属性的另一种调用方式：对象[‘属性名’]，注意方括号里面的属性必须加引号，我们后面会用
对象里面的方法调用：对象方法名()，注意这个方法名字后面一定加括号

```
console.log(star.name)
//调用名字属性
console.log(star['name']) // 调用名字属性
star.sayHi();
//调用 sayHi 方法,注意，一定不要忘记带后面的括号

```



变量、属性、函数、方法总结
变量：单独声明赋值，单独存在
属性：对象里面的变量称为属性，不需要声明，用来描述该对象的特征.
函数：单独存在的，通过“函数名()” 的方式就可以调用
方法：对象里面的函数称为方法，方法不需要声明，使用“对象.方法名()”的方式就可以调用，方法用来描述该对象
的行为和功能。



#####  利用 new Object 创建对象

```
var obj = new Object();//O要大写
创建了一个空的对象
obj.uname =‘张三疯";
obj.age = 18;
obj.sex ='男';
obj.sayHi = function(){
console.log('hi~');
}
```

（1）我们是利用 等号 = 赋值的方法 添加对象的属性和方法
（2）每个属性和方法之间用 分号结束		

```
console.log(obj.uname);
			console.log(obj['sex']);
			obj.sayHi();

```



#####  构造函数的语法格式

```
// function 构造函数名() {
//this.属性 = 值;
//this .方法 = function(){}
// }

```

```
实例：
// var 新建的对象=new 构造函数名();
function Star(uname, age, sex) {
this.name = uname;
this.age = age;
this.sex = sex;
this.sing = function(sang) {
console.log(sang);
 }
}

var ldh = new Star("刘德华', 18，'男');// 调用函数返回的是一个对象
// console.log(typeof ldh);
console.log(ldh.name);
console.log(ldh['sex']);
ldh.sing("冰雨");
var zxy = new Star("张学友', 19，"男");
console.log(zxy.name);
console.log(zxy.age);
zxy.sing("李香兰');


```

// 1．构造函数名字首字母要大写
// 2．我们构造函数不需要return 就可以返回结果
// 3．我们调用构造函数 必须使用 new
// 4．我们只要new Star(）调用函数就创建一个对象 ldh{}
// 5．我们的属性和方法前面必须添加 this



##### 构造函数和对象

构造函数，如Stars()，抽象了对象的公共部分，封装到了函数里面，它泛指某一大类（class）
创建对象，如 new Stars()，特指某一个，通过 new关键字创建对象的过程我们也称为对象实例化



##### new在执行时会做四件事情：

1. 在内存中创建一个新的空对象。
2. 让 this 指向这个新的对象。
3. 执行构造函数里面的代码，给这个新对象添加属性和方法。
4. 返回这个新对象（所以构造函数里面不需要return）。



##### for in 遍历对象

```
for(变量 in 函数)

for (var k in obj) {
console.log(k)；// k 变量 输出 得到的是 属性名
console.log(obj[k])；// obj[k] 得到是 属性值
// 我们使用 for in 里面的变量 我们喜欢写 k 或者 key
}
```



##### 内置对象

JavaScript中的对象分为3种：自定义对象、内置对象、浏览器对象
前面两种对象是JS基础内容，属于ECMAScript；第三个浏览器对象属于我们JS独有的
内置对象就是指JS 语言自带的一些对象，这些对象供开发者使用，并提供了一些常用的或是最基本而必要的功能（属性和方法）
内置对象最大的优点就是帮助我们快速开发

 JavaScript提供了多个内置对象：Math、Date 、Array、string等



##### MDN

学习一个内置对象的使用，只要学会其常用成员的使用即可，我们可以通过查文档学习，可以通过MDN/W3C
来查询。
Mozilla 开发者网络（MDN）提供了有关开放网络技术（Open Web）的信息，包括HTML、CSS和万维网及
HTML5 应用的 API。
MDN: https://developer.mozilla.orq/zh-CN/



##### Date概述

Date 对象和Math 对象不一样，他是一个构造函数，所以我们需要实例化后才能使用
Date 实例用来处理日期和时间



#####  Date()方法的使用

1. 获取当前时间必须实例化

  ```
  var now = new Date();
  console.log(now);
  ```

  

2. Date0 构造函数的参数
如果括号里面有时间，就返回参数里面的时间。例如日期格式字符串为'2019-5-1’，可以写成new Date（'2019-5-1 22:07:00'）
或者 new Date( '2019/5/1 22:07:00')



##### Date 总的毫秒数

```
获得Date总的毫秒数(时间戳) 不是当前时间 而是距离1970年1月1号过了多少毫秒数
// 1.通过 valueOf() 或getTime(）
var date = new Date();
console.log(date.value0f()；// 就是 我们现在时间 距离197e.1.1 总的亳秒数
console.log(date.getTime());
// 2．简单的写法（最常用的写法）
var date1 = +new Date(); // +new Date()
返回的就是总的毫秒数
console.log(date1);
// 3．H5 新增的 获得总的毫秒数
console.log(Date.now());

```

#####  检测是否为数组

```
//（1）instanceof 运算符 它可以用来检测是否为数组
var arr = [];
var obj = {};
console.log(arr instanceof Array);

console.log(obj instanceof Array);

// (2) Array.isArray(参数)； H5新增的方法 ie9以上版本支持

console.log(Array.isArray(arr));

console.log(Array.isAnray(obj));

```



##### 添加删除数组元素的方法

方法名										说明																							 返回值

------

push(参数1....)				末尾添加一个或多个元素，注意修改原数组									 并返回新的长度
pop()								删除数组最后一个元素，把数组长度减1无参数、修改原数组		返回它删除的元素的值
unshift(参数1...)			  向数组的开头添加一个或更多元素，注意修改原数组					  并返回新的长度
shift()							删除数组的第一个元素，数组长度减1无参数、修改原数组				并返回第一个元素的值

------

```
push(）在我们数组的末尾 添加一个或多个元素
var arr = [1, 2, 3];
// arr.push(4, 'pink');
console.log(anr.push(4, 'pink'));
console.log(arr);
// (1) push 是可以给数组追加新的元素
//（2）push（）参数直接写 数组元素就可以了
//（3）push完毕之后，返回的结果是 新数组的长度
//（4）原数组也会发生变化
// 2．unshift 在我们数组的开头 添加一个或者多个数组元素
console.log(arr.unshift('red", "purple'));
console.log(arr);
//（1）unshift是可以给数组前面追加新的元素
// (2) unshift(）参数直接写 数组元素就可以了
//（3）unshift完毕之后，返回的结果是 新数组的长度
//（4）原数组也会发生变化
```



##### 数组排序

方法名								说明																是否修改原数组

------

reverse()							颠倒数组中元素的顺序,无参数					该方法会改变原来的数组 返回新数组
sort()								  对数组的元素进行排序								 该方法会改变原来的数组 返回新数组

------

```
// 数组排序

// 1. 翻转数组

var arr = ["pink', 'red', 'blue'];
arr.reverse();
console.log(arr);

// 2．数组排序（冒泡排序）

var arr1 = [13, 4, 77, 1, 7];

arr1.sort(function(a, b) {

return a - b；// 升序的顺序排列

return b - a；// 降序的顺序排列

});

console.log(arr1);
```



##### 数组索引方法

方法名					 说明																	返回值

------

indexOf（）				数组中查找给定元素的第一个索引				如果存在返回索引号 如果不存在，则返回-1。
lastindexOf()			在数组中的最后一个的索引						 如果存在返回索引号 如果不存在，则返回-1。

------

```
// 返回数组元素索引号方法 indexof(数组元素) 作用就是返回该数组元素的索引号 从前面开始查找
// 它只返回第一个满足条件的索引号
// 它如果在该数组里面找不到元素，则返回的是 -1
var anr = ['red", 'green', 'pink'];
console.log(arr.indexof('blue'));
// 返回数组元素索引号方法 lastIndexOf(数组元素） 作用就是返回该数组元素的索引号 从后面开始查找

```



#####  数组转换为字符串

```
// 1. tostring()将我们的数组转换为字符串
var arr = [1, 2, 3];
console.log(arr.tostring())；// 1,2,3
// 2.join(分隔符)
var arr1 = ['green', "blue', 'pink'];
console.log(arr1.join()); // green,blue,pink
console.log(arr1.join('-')); // green-blue-pink
console.log(arr1.join('&")); // green&blue&pink

```

##### 其它常用数组方法

方法名				说明																			返回值

------

concat()			 连接两个或多个数组 不影响原数组						返回一个新的数组
slice()				数组截取slice(begin, end)									    返回被截取项目的新数组
splice()			  数组删除splice(第几个开始,要删除个数)				 返回被删除项目的新数组 注意，这个会影响原数组。

------

slice() 和 splice() 目的基本相同，建议同学们重点看下splice()



#####  基本包装类型

为了方便操作基本数据类型，JavaScript还提供了三个特殊的引用类型：String、Number和Boolean。
基本包装类型就是把简单数据类型包装成为复杂数据类型，这样基本数据类型就有了属性和方法。
//下面代码有什么问题？
var str = 'andy';
console.log(str.length);
按道理基本数据类型是没有属性和方法的，而对象才有属性和方法，但上面代码却可以执行，这是因为js 会把
基本数据类型包装为复杂数据类型，其执行过程如下：

```
//1.生成临时变量，把简单类型包装为复杂数据类型
var temp = new string('andy");
//2. 赋值给我们声明的字符变量
str = temp;
//3.销毁临时变量
temp = null;
```



### 字符串对象

##### 字符串的不可变

指的是里面的值不可变，虽然看上去可以改变内容，但其实是地址变了，内存中新开辟了一个内存空间。



#####  根据字符返回位置

字符串所有的方法，都不会修改字符串本身(字符串是不可变的)，操作完成会返回一个新的字符串。
方法名															说明

------

indexOf("要查找的字符,开始			返回指定内容在元字符串中的位置，如果找不到就返回-1，开始的位置是
的位置)												index索引号

lastindexOf（）									从后往前找,只找第一个匹配的

------



##### 根据位置返回字符（重点）

方法名									说明																			使用

------

charAt(index)					返回指定位置的字符(index 字符串的索引号)			str.charAt(0)
charCodeAt(index)			获取指定位置处字符的ASCII码(index索引号)			str.charCodeAt(0)
str[index]							获取指定位置处字符											HTML5，IE8+支持和charAt()等效

------



#####  字符串操截取作方法（重点）

方法名													说明

------

concat(str1,str2,str3...)					concat()方法用于连接两个或多个字符串。拼接字符串，等效于+，+更常用
substr(start,length)						从start位置开始（索引号）**length 取的个数 重点记住这个**
slice(start, end)								从start位置开始，截取到end位置，end取不到(他们俩都是索引号)
substring(start, end)					从start位置开始，截取到end位置，end取不到 基本和slice 相同 但是不接受负值

------



```
// 1. 替换字符 replace('被替换的字符',‘替换为的字符') 它只会替换第一个

var str = 'andyandy';
console.log(str.replace('a', 'b'));
实例：// 有一个字符串 'abcoefoxyozzopp'要求把里面所有的 o替换为*
var str1 = 'abcoefoxyozzopp'; 
while (str1.index0f('o') !== -1) {
str1 = str1.replace('o', '*');
console.log(str1);
// 2. 字符转换为数组 split("分隔符')
前面我们学过join 把数组转换为字符串
var str2 = 'red, pink, blue';
console.log(str2.split(","));
var str3 = 'red&pink&blue';
console.log(str3.split('&'));
```

#####  其它重要操作符

toUpperCase（） //转换大写
toLowerCase（） //转换小写



##### 经典案例：找出字符串中出现次数最多的字符

```
    var str = "abaasdffggghhjjkkgfddsssss3444343";
 var fre = new Object();
    var chars = "",
      max = "";
    var a = 0;
    for (var i = 0; i < str.length; i++) {
      chars = str.charAt(i);
      if (chars in fre) {
        fre[chars]++;
      } else {
        fre[chars] = 1;
      }
    }
    for (var k in fre) {
      if (fre[k] > a) {
        a = fre[k];
        max = k;
      }
    }
    console.log(max + a);
```



### 简单类型与复杂类型

简单类型又叫做基本数据类型或者值类型，复杂类型又叫做引用类型。
值类型：简单数据类型/基本数据类型，在存储时变量中存储的是值本身，因此叫做值类型

###### 其中null比较特殊

 简单数据类型 null 返回的是一个空的对象 object

```
var timer = null;
console.log(typeof timer);
```

// 如果有个变量我们以后打算存储为对象,暂时没想好放啥，这时候我们就给他赋值为null。


#####  复杂类型的内存分配

引用类型（复杂数据类型）：通过new关键字创建的对象（系统对象、自定义对象），如Object、Array、Date等
引用类型变量（栈空间）里存放的是地址，真正的对象实例存放在堆空间中



##### 简单数据类型的传参

函数的形参也可以看做是一个变量，当我们把一个值类型变量作为参数传给函数的形参时，其实是把变量在栈
空间里的值复制了一份给形参，那么在方法内部对形参做任何修改，都不会影响到的外部变量。

```
function fn(a) {
a++;
console.log(a);
}
var x = 10;
fn(x);
console.log(x);
```



##### 复杂数据类型的传参

函数的形参也可以看做是一个变量，当我们把引用类型变量传给形参时，其实是把变量在栈空间里保存的堆地
址复制给了形参，形参和实参其实保存的是同一个堆地址，所以操作的是同一个对象。

```
function Person(name)
this name = name;
function f1(x) ( // x = p
console.log(x.name)；// 2.这个输出什么？
x.name = "张学友";
console.log(x.name)；// 3.这个输出什么？
var p = new Person("刘德华");
console.log(p.name);// 1.这个输出什么 ？
f1(p);
console.log(p.name);// 4.这个输出什么 ？
```



### API 和 Web API



#####  API

API（Application Programming Interface,应用程序编程接口）是一些预先定义的函数，目的是提供应用程序
与开发人员基于某软件或硬件得以访问一组例程的能力，而又无需访问源码，或理解内部工作机制的细节。
简单理解：API是给程序员提供的一种工具，以便能更轻松的实现想要完成的功能。
比如手机充电的接口：
我们要实现充电这个功能：
● 我们不关心手机内部变压器，内部怎么存储电等
● 我们不关心这个充电线怎么制作的
● 我们只知道，我们拿着充电线插进充电接口就可以充电
   这个充电接口就是一个API



#####  API 和 Web API总结

1. API 是为我们程序员提供的按口，帮助我们实现某种功能，我们会使用就可以了，不必纠结内部如何实现
2. Web API 主要是针对于浏览器提供的接口，主要针对于浏览器做交互效果。
3. Web API一般都有输入和输出（函数的传参和返回值），Web API 很多都是方法（函数）
4. 学习 Web API可以结合前面学习内置对象方法的思路学习



#####  Web API

Web API 是浏览器提供的一套操作浏览器功能和页面元素的 API（BOM和 DOM）。
现阶段我们主要针对于浏览器讲解常用的API,主要针对浏览器做交互效果。
比如我们想要浏览器弹出一个警示框，直接使用alert(‘弹出’)
MDN详细 API: https://developer.mozilla.org/zh-CN/docs/Web/API
因为Web API 很多，所以我们将这个阶段称为Web APIs



##### DOM树

文档：一个页面就是一个文档，DOM 中使用 document表示
元素：页面中的所有标签都是元素，DOM中使用element 表示
节点：网页中的所有内容都是节点（标签、属性、文本、注释等），DOM中使用node 表示

**DOM把以上内容都看作是对象**



### DOM

##### 获取元素

DOM在我们实际开发中主要用来操作元素。

###### 获取页面中的元素可以使用以下几种方式:

根据 ID 获取

使用 getElementByld()方法可以获取带有ID的元素对象。根据标签名获取

```
// 1．因为我们文档页面从上往下加载，所以先得有标签 所以我们script写到标签的下面
// 2．get： 获得 element ：  元素 by ： 通过  getElementByld()严格区分大小写
// 3．参数 id是大小写敏感的字符串
// 4．返回的是一个元素对象
var timer = document.getElementById('time');
console.log(timer);
console.log(typeof timer);
// 5．console.dir 打印我们返回的元素对象，更好的查看里面的属性和方法。
console.dir(timer);
```



 根据标签名获取
使用 getElementsByTagName()方法可以返回带有指定标签名的对象的集合。

```
document.getElementsByTagName("标签名");
```



还可以获取某个元素(父元素)内部所有指定标签名的子元素。
element.getElementsByTagName（"标签名"）：


注意：

1. 因为得到的是一个对象的集合。，所以我们需要操作里面的元素就需要遍历。

2. 得到元素对象是动态的（可变的）

3. 父元素必须是单个对象(必须指明是哪一个元素对象),获取的时候不包括父元素自己。

   

```
// 1.返回的是 获取过来元素对象的集合 以伪数组的形式存储的
var lis = document.getElementsByTagName('li');
console.log(lis);
console.log(lis[0]);
// 2．我们想要依次打印里面的元素对象我们可以采取遍历的方式
for (var i = e; i < lis.length; i++) {
console.log(lis[i]);
}
// 3．如果页面中只有一个1i 返回的还是伪数组的形式
// 4．如果页面中没有这个元素 返回的是空的伪数组的形式
// 5. element.getElementsByTagName('标签名')；父元素必须是指定的单个元素
// var ol = document.getElementsByTagName('ol')；// [ol]
// console.log(ol[0].getElementsByTagName('li'));
var ol = document.getElementById('ol');
console.log(ol.getElementsByTagName('li'));
```



通过 HTML5新增的方法获取
特殊元素获取











