# JavaScript核心基础



### JavaScript 入门

#### 一、输出语句

JS 中经常使用的输出语句有三种：

##### alert ：

在浏览器中以 **页面警示框** 的形式弹出展示输出。

```js
alert('输出方式一');
```

![输出方式一](https://github.com/DemonForNi/JS_Basics/blob/main/image/image-20230219222016057.png)



##### console.log() ：

在浏览器中以 **浏览器控制台 **的形式展示输出。

```js
console.log('输出方法二');
```

![输出方式二](https://github.com/DemonForNi/JS_Basics/blob/main/image/image-20230219222056930.png)



##### document.write() ：

在浏览器中以 **浏览器页面内容(页面文档)** 的形式展示输出。

```js
document.write('输出方法三');
```

![输出方式三](https://github.com/DemonForNi/JS_Basics/blob/main/image/image-20230219222135513.png)

------





#### 二、编写位置

JS 代码的编写位置有三种：

##### 内部  JS ：

编写在网页内部的 script 标签中

```html
<script type="text/javascript">
    console.log('内部书写');
</script>
```

type="text/javascript"  可省略不写，type 默认值为 text/javascript



##### 外部  JS ：

编写在网页外部的 JS 文件中，在使用时通过 script 标签引入

```html
<script src="./script/script.js"></script>
```



##### 指定属性中的  JS ：

编写在网页内部标签的指定属性中

```html
<button onclick="console.log('点击');">点击</button>
<button onmouseenter="console.log('鼠标进入');"></button>

<a href="javascript:console.log('跳转');">超链接</a>

<a href="javascript:;">超链接</a>
```

------





#### 三、基本语法

JS 代码中有以下一些基础语法：

##### 注释：

注释分为 **多行注释** 和 **单行注释** ，注释中的内容会被解释器 **忽略** ，可以通过注释对代码进行解释说明，也可以通过注释来注释不需要或者不被执行的代码。

多行注释 ：多行注释的注释内容写在  /*  */  内部

```js
/*
	多行注释
	多行注释
	多行注释
*/
```

单行注释：单行注释的注释内容写在 `//` 之后

```js
// 单行注释 单行注释 单行注释
```



##### 严格区分大小写：

JS 代码在书写时 **严格区分大小写** ，当代码大小写书写错误时，将会导致程序在运行时 **产生报错信息** ，并 **阻止** 后续代码继续执行。

```js
alert(123456) // 正确书写格式

Alert(123456) // 错误书写格式，控制台产生报错信息 Uncaught ReferenceError: Alert is not defined
```



##### 多个空格和换行会被忽略：

JS 代码中书写 **多个空格和换行** 在被编译执行是会被忽略，可以利用这个特点对代码进行格式化，提高代码的可读性。

```js
console.log( 123456 );

console.log
(
	123456
);
```

以上两段代码的最终执行结果都是相同的，都会在控制台中输出： 123456

![多个空格和换行被忽略](https://github.com/DemonForNi/JS_Basics/blob/main/image/image-20230219230931793.png)



##### 每条语句都应以分号结束：

JS 代码中的每一条语句都应该以 **分号结尾** ， JS 具有自动添加分号的功能，如果语句结束后未书写分号，解释器会自动添加分号使代码语句完整，但是，**某些极少数的情况** 下，解释器自动添加分号会使得代码执行出错，发生这种情况时，可以通过纠正代码格式等一些方法处理这种 **罕见的错误** 。

```js
console.log(654321)

console.log(654321);
```

以上两段代码的最终执行结果都是相同的，都会在控制台中输出： 654321

![语句分号结束](https://github.com/DemonForNi/JS_Basics/blob/main/image/image-20230219233319216.png)

------





#### 四、字面量 和 变量

##### 字面量：

字面量其实就是 **一个值** ，它所代表的含义就是它 **字面的意思** 。比如：1  2  100  “字面量”   true  null  ........  

在 JS 中，所有字面量都可以直接使用，但是直接使用字面量并不方便。

```js
console.log(1, 2, "字面量", true, null);
```

上述代码的最终执行结果：在控制台输出： 1 2 '字面量' true null

![字面量](https://github.com/DemonForNi/JS_Basics/blob/main/image/image-20230219234745504.png)



##### 变 量：

JS 中的变量 **不会受到字面量类型的限制** ，可以用于 **“存储”** 任何字面量，并且变量存储的字面量可以 **随意修改** ，通过变量可以对字面量进行 **描述** ，并且变量方便修改。

```js
a = 123;
a = "变量";
age = 18;
weight = 75;
```



##### 变量的使用：

变量的声明：var  变量名  /  let  变量名

变量的复制：变量名 = XXXX

变量的声明和赋值可以进行：var  变量名 = XXXX   /   let  变量名 = XXXX

```js
var a;
var b;
var c;
var aa, bb, cc;

let aaa, bbb, ccc;

let age = 18;
console.log(age);
age = 20;
console.log(age);
```

上述代码最终执行结果：在控制台输出： 18  20

![变量的使用](https://github.com/DemonForNi/JS_Basics/blob/main/image/image-20230220000240481.png)



##### 变量的内存结构：

变量中不存储任何值，而是存储 **值的内存地址** 。

```js
let a = "变量"
let b = "变量"
let c = d = 123
let e = f = false
```

| 变量名称 | 值 (值的内存地址) |
| :------- | ----------------- |
| a        | 0x11              |
| b        | 0x11              |
| c        | 0x22              |
| d        | 0x22              |
| e        | 0x33              |
| f        | 0x33              |

| 值     | 内存地址 |
| ------ | :------- |
| "变量" | 0x11     |
| 123    | 0x22     |
| false  | 0x33     |

------





#### 五、常量

JS 中使用 **const** 来声明常量，常量在声明时必须同时赋值，并且 **只能赋值一次** ，不可以进行二次赋值，否则会导致程序报错。

JS 中除了常规的常量(圆周率 PI)外，还有一些对象类型的数据也会声明为常量，人为的让这些数据不被修改。

```js
const Pi = 3.1415;
Pi = 10;  // Uncaught TypeError: Assignment to constant variable.
console.log(Pi);
```

------





#### 六、标识符

JS 中所有可以人为 **自主命名** 的内容，都可以认为是一个标识符。比如：变量名、函数名、类名 ......

```js
let a = 10; // a 为一个标识符
```

标识符命名有如下规范：

1. 标识符只能含有字母、数字、下划线、$，且不能以数字开头
2. 标识符不能是 JS 中的 **[关键字](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Lexical_grammar#%E5%85%B3%E9%94%AE%E5%AD%97)** 和 **[保留字](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Lexical_grammar#%E5%85%B3%E9%94%AE%E5%AD%97)** ，也不建议使用 **内置函数名或类名** 作为变量名
3. 命名规范：

- 变量通常使用小驼峰命名法，首字母小写，每个单词首字母大写，比如：maxLength，boredLeftWidth ....
- 类名通常使用大驼峰命名法，所有单词首字母大写，比如：MaxLength，GetSum，GetName ....
- 常量通常所有单词字母全部大写，比如：PI，MAX_LENGTH，MIN_HEIGHT ....

```js
let aa$ = 123;
let $_aaa = 123;
let $123_aaa = 123;
```



不遵守标识符命名规范将会导致代码报错。

```js
let @#123$aaa = 123; // Uncaught SyntaxError: Invalid or unexpected token

let let = 123; // Uncaught SyntaxError: let is disallowed as a lexically bound name

let alert = 55;
alert(123); // Uncaught TypeError: alert is not a function
```

------





### 数据类型

#### 一、数值

##### Number ( 数值 )

JS 中所有的整数和浮点数都是 Number 类型。

```js
let a = 10;
let b = 3.1415;
```



 JS 中的数值不会无限大，当数值超过一定范围后会显示近似值。

```js
let a = 99999999999999911;
console.log(a); // 99999999999999900

let b = 1.111111111111111111111111111;
console.log(b); // 1.1111111111111112

let c = 0.00000000000000000001;
console.log(c); // 1e-20
```

控制台中输出的 a 值为： 99999999999999900

控制台中输出的 b 值为： 1.1111111111111112

控制台中输出的 c 值为： 1e-20

![image-20230220222316289](https://raw.githubusercontent.com/DemonForNi/JS_Basics/blob/main/image/image-20230220222316289.png)



`Infinity` 是一个特殊的数值，表示为 **无穷 **。

```js
let b = 99999 ** 99999; // ** 为幂运算
console.log(b); // Infinity
```

此时，控制台中输出的 b 值为：`Infinity`

![image-20230220221053676](https://raw.githubusercontent.com/DemonForNi/JS_Basics/blob/main/image/image-20230220221053676.png)

**！！注意：在 JS 中进行一些精度比较高的运算时要十分注意**



NaN 是一个特殊的数值，表示 **不是一个数值** ( Not  a  Number ) ，非法数值。

```js
let s = 1 - "aaa";
console.log(s); // NaN
```

此时，控制台中输出的 s 的值为：NaN

![image-20230220223317226](https://raw.githubusercontent.com/DemonForNi/JS_Basics/blob/main/image/image-20230220223317226.png)



##### BigInt ( 大整数 )

BigInt  用来表示一些比较大的整数，使用 n 结尾。BigInt 可以表示的数值范围 **依据内存大小判断** 。

```js
let bigInt = 99999999999999999999999999999n;
console.log(bigInt); // 99999999999999999999999999999n
```

此时，控制台中输出的 bigInt 的值为：99999999999999999999999999999n

![image-20230220224436686](https://raw.githubusercontent.com/DemonForNi/JS_Basics/blob/main/image/image-20230220224436686.png)



##### 进制数值

二进制数值：以  0b 开头

八进制数值：以 0o  开头

十六进制数值：以  0x  开头

```js
let i = 0b1010;
let j = 0o10;
let k = 0xff;
console.log(i, j, k);
```

数值在表示时可以使用其他进制的表示方法，最终在控制台输出的结果都是十进制的数值。

此时，控制台中输出的  i  j  k  的值为：10	8	255

![image-20230220225314633](https://raw.githubusercontent.com/DemonForNi/JS_Basics/blob/main/image/image-20230220225314633.png)

------





#### 二、类型检查  typeof  运算符

typeof 运算符 用来检查不同的值的类型，根据不同的值返回不同的结果。

```js
let a = 10;
let b = 10n;
console.log(typeof a);
console.log(typeof b);
```

控制台中输出：

a 变量的值的类型：number

b 变量的值的类型：bigint

![image-20230220230841439](https://raw.githubusercontent.com/DemonForNi/JS_Basics/blob/main/image/image-20230220230841439.png)

------





#### 三、字符串

##### 字符串

在 JS 中使用 **单引号** 或 **双引号** 来表示字符串。

```js
let str = "AAAA";
let str2 = '你好！';
console.log(str);
console.log(str2);
```

控制台中输出：

str ：AAAA		str2 ：你好！

![image-20230220231519807](https://raw.githubusercontent.com/DemonForNi/JS_Basics/blob/main/image/image-20230220231519807.png)



##### 转义字符	\

\\"  ==>  "		\\'  ==>  '		\\\  ==>  \		\\t  ==>  制表符		\\n  ==>  换行

```js
let a = '这是一个\"字符串';
console.log(a);
```

控制台中输出：这是一个\"字符串

![image-20230220232343254](https://raw.githubusercontent.com/DemonForNi/JS_Basics/blob/main/image/image-20230220232343254.png)



##### 模板字符串

使用反单引号 ` 来表示模板字符串。模板字符串中可以 **嵌入** 变量。

```js
let name = 'AAAA';
let strs = `你好！${name}`;
console.log(strs);
```

控制台中输出：你好！AAAA

![image-20230220233524842](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230220233524842.png)



**使用 typeof 检查一个字符串时会返回 string**

```js
let b = "aaaaa";
console.log(typeof b);
```

控制台中输出：string

![image-20230220233621446](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230220233621446.png)



