# JavaScript核心基础



### 一、输出语句

JavaScript 中经常使用的输出语句有三种：

#### `alert` ：

在浏览器中以 **页面警示框** 的形式弹出展示输出。

```js
alert('输出方式一');
```

![输出方式一](https://github.com/DemonForNi/JS_Basics/blob/main/image/image-20230219222016057.png)



#### `console.log()`：

在浏览器中以 **浏览器控制台 **的形式展示输出。

```js
console.log('输出方法二');
```

![输出方式二](https://github.com/DemonForNi/JS_Basics/blob/main/image/image-20230219222056930.png)



#### `document.write()` ：

在浏览器中以 **浏览器页面内容(页面文档)** 的形式展示输出。

```js
document.write('输出方法三');
```

![输出方式三](https://github.com/DemonForNi/JS_Basics/blob/main/image/image-20230219222135513.png)

------





### 二、编写位置

JavaScript 代码的编写位置有三种：

#### 内部 `JS`：

编写在网页内部的 `script` 标签中

```html
<script type="text/javascript">
    console.log('内部书写');
</script>
```

`type="text/javascript"` 可省略不写，`type` 默认值为 `text/javascript`



#### 外部 `Js`：

编写在网页外部的 `JS` 文件中，在使用时通过 `script` 标签引入

```html
<script src="./script/script.js"></script>
```



#### 指定属性中的 `JS`：

编写在网页内部标签的指定属性中

```html
<button onclick="console.log('点击');">点击</button>
<button onmouseenter="console.log('鼠标进入');"></button>

<a href="javascript:console.log('跳转');">超链接</a>

<a href="javascript:;">超链接</a>
```

------





### 三、基本语法

JavaScript 代码中有以下一些基础语法：

#### 注释：

注释分为 **多行注释** 和 **单行注释** ，注释中的内容会被解释器 **忽略** ，可以通过注释对代码进行解释说明，也可以通过注释来注释不需要或者不被执行的代码。

多行注释 ：多行注释的注释内容写在 `/* */` 内部

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



#### 严格区分大小写：

JavaScript 代码在书写时 **严格区分大小写** ，当代码大小写书写错误时，将会导致程序在运行时 **产生报错信息** ，并 **阻止** 后续代码继续执行。

```js
alert(123456) // 正确书写格式

Alert(123456) // 错误书写格式，控制台产生报错信息 Uncaught ReferenceError: Alert is not defined
```



#### 多个空格和换行会被忽略：

JavaScript 代码中书写 **多个空格和换行** 在被编译执行是会被忽略，可以利用这个特点对代码进行格式化，提高代码的可读性。

```js
console.log( 123456 );

console.log
(
	123456
);
```

以上两段代码的最终执行结果都是相同的，都会在控制台中输出： 123456

![多个空格和换行被忽略](https://github.com/DemonForNi/JS_Basics/blob/main/image/image-20230219230931793.png)



#### 每条语句都应以分号结束：

JavaScript 代码中的每一条语句都应该以 **分号结尾** ， JavaScript 具有自动添加分号的功能，如果语句结束后未书写分号，解释器会自动添加分号使代码语句完整，但是，**某些极少数的情况** 下，解释器自动添加分号会使得代码执行出错，发生这种情况时，可以通过纠正代码格式等一些方法处理这种 **罕见的错误** 。

```js
console.log(654321)

console.log(654321);
```

以上两段代码的最终执行结果都是相同的，都会在控制台中输出： 654321

![语句分号结束](https://github.com/DemonForNi/JS_Basics/blob/main/image/image-20230219233319216.png)

------





### 四、字面量 和 变量

#### 字面量：

字面量其实就是 **一个值** ，它所代表的含义就是它 **字面的意思** 。比如：1  2  100  “字面量”   true  null  ........  

在 JavaScript 中，所有字面量都可以直接使用，但是直接使用字面量并不方便。

```js
console.log(1, 2, "字面量", true, null);
```

上述代码的最终执行结果：在控制台输出： 1 2 '字面量' true null

![字面量](https://github.com/DemonForNi/JS_Basics/blob/main/image/image-20230219234745504.png)



#### 变 量：

JavaScript 中的变量 **不会受到字面量类型的限制** ，可以用于 **“存储”** 任何字面量，并且变量存储的字面量可以 **随意修改** ，通过变量可以对字面量进行 **描述** ，并且变量方便修改。

```js
a = 123;
a = "变量";
age = 18;
weight = 75;
```



#### 变量的使用：

变量的声明：`var`  变量名  /  `let`  变量名

变量的复制：变量名 = `XXXX`

变量的声明和赋值可以进行：`var`  变量名 = `XXXX`   /   `let`  变量名 = `XXXX`

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

![变量的使用](https://github.com/DemonForNi/JS_Basics/blob/main/image-20230220000240481.png)






