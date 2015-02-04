# JavaScript 编码规范


[1. 代码格式](#user-content-1-代码格式)

　　[1.1 缩进](#user-content-11-缩进)

　　[1.2 空格](#user-content-12-空格)

　　[1.3 行的长度与换行](#user-content-13-行的长度与换行)

　　[1.4 空行](#user-content-14-空行)

　　[1.5 语句](#user-content-15-语句)

[2. 命名](#user-content-2-命名)

[3. 注释](#user-content-3-注释)

　　[3.1 单行注释](#user-content-31-单行注释)

　　[3.2 多行注释](#user-content-31-多行注释)

　　[3.3 文档注释](#user-content-33-文档注释)

　　[3.4 特殊注释](#user-content-34-特殊注释)

[4. 语言特性](#user-content-4-语言特性)

　　[4.1 基础数据类型](#user-content-41-基础数据类型)

　　　　[4.1.1 字符串\[String\]](#user-content-411-字符串string)

　　　　[4.1.2 数\[Number\]](#user-content-412-数number)

　　　　[4.1.3 Null](#user-content-413-null)

　　　　[4.1.4 Undefined](#user-content-414-undefined)

　　[4.2 引用类型](#user-content-42-引用类型)

　　　　[4.2.1 对象\[Object\]](#user-content-421-对象object)

　　　　[4.2.2 数组\[Array\]](#user-content-422-数组array)

　　[4.3 变量](#user-content-43-变量)

　　[4.4 函数](#user-content-44-函数)

　　[4.5 运算符](#user-content-45-运算符)

　　[4.6 语句](#user-content-46-语句)

　　　　[4.6.1 条件语句](#user-content-461-条件语句)

　　　　[4.6.2 循环语句](#user-content-462-循环语句)

　　　　[4.6.3 with 语句](#user-content-463-with-语句)

　　[4.7 动态特性](#user-content-47-动态特性)


## 1. 代码格式

### 1.1 缩进

使用 2 个空格做为一个缩进层级，不允许使用 4 个空格 或 tab 字符。

```javascript
// Bad
if (a && b) {
  for (i = 0, i < 10; i++) {
    alert(i);
  }
}

// Good
if (a && b) {
  for (i = 0, i < 10; i++) {
    alert(i);
  }
}

```


### 1.2 空格

- 二元运算符两侧必须有一个空格，一元运算符与操作对象之间不允许有空格
- - 用作代码块起始的左花括号 `{` 前必须有一个空格
- `if` / `else` / `for` / `while` / `function` / `switch` / `do` / `try` / `catch` / `finally` 关键字后，必须有一个空格
- 函数声明、函数表达式、函数调用中，函数名和 ( 之间不允许有空格

```javascript
// Bad
if(a+b === 0 && !c){
  allowed ();
}

// Good
if (a + b === 0 && !c) {
  allowed();
}
```

- 在对象创建时，属性中的 `:` 之后必须有空格，`:` 之前不允许有空格
- `,` 和 `;` 前不允许有空格
- 多数情况下 `()` 、`[]` 和 `{}` 内紧贴括号部分不允许有空格（换行不算空格）
- 行尾不要有空格。

```javascript
// Bad
var obj = {
  a:1 ,
  b : 2
};

var obj2 = { c: 3 };

// Good
var obj = {
  a: 1,
  b: 2
};

var obj2 = {c: 3};
```


### 1.3 行的长度与换行

- 每行不得超过 `120` 个字符(正则表达式例外)，超过务必换行。
- 通常在运算符后面换行，下一行增加两个层级（该规范指 `4` 个空格）的缩进；例外的是，给变量赋值的时候，第二行位置应当和赋值运算符位置保持对齐。
- 每个独立语句结束后换行。

```javascript
// Bad
callAFunction(document, element, window, "some string value", true, 123,
  navigator);

callAFunction(document, element, window, "some string value", true, 123
    , navigator);

var html = "<pThe sum of " + a + " and " + b + " plus " + c
           + " is " + (a + b + c);

// Good
callAFunction(document, element, window, "some string value", true, 123,
    navigator);

var html = "<pThe sum of " + a + " and " + b + " plus " + c +
           " is " + (a + b + c);
```


### 1.4 空行

- 函数之间
- 函数中局部变量和第一行语句之间
- 多行或单行注释之前
- 在函数内逻辑上独立的代码片段之间使用空行分隔

```javascript
// Bad
function total() {
  var i = 100;
  if (i < 10) {
    
  } 
  // description
  return false;
}
function add() {
}

// Good
function total() {
  var i = 100;

  // description
  if (i < 10) {
  }
  
  // description
   return false;
}

function add() {
}
```


### 1.5 语句

- 不要省略语句结束的分号
- 在 `if` / `else` / `for` / `do` / `while` 语句中，即使只有一行，也不要省略 `{}`，并且推荐使用 `{}` 也不要写为单行

```javascript
// Bad
function total() {
  if (i < 10) hello();
  else {hi()};
}

// Good
function total() {
  if (i < 10) {
    hello();
  }
}
```

- 花括号的对齐采用末尾追加，不要换行

```javascript
// Bad
function doSomething() 
{
  // do something
}

// Good
function doSomething() {
  // do something
}
```


## 2. 命名

- 变量名应当遵守 `Camel` 命名法，并且命名前缀应当是名词

```javascript
// Good
var count = 10;
var myName = "c";
```

- 函数命名应当遵守 `Camel` 命名法，命名前缀应当是动词

```javascript
// Good
function hasText() {}
function total() {}
```

下面是函数命名中一些常见的动词约定：

| 动词 |  含义 |
| ---- | -------------------- |
| can  |  函数返回一个BOOL值|
| has  |  函数返回一个BOOL值|
| is   |  函数返回一个BOOL值|
| get  |  函数返回一个非BOOL值|
| set  |  函数用来保存一个值|

- 常量名使用大写字母和下划线命名

```javascript
// Good
var MAX_COUNT = 10;
var URL = "http://";
```

- 构造函数命名使用 `Pascal` 命名法，由于用来创建实例，所以一般是名词。
- 构造函数的方法和属性使用 `Camel` 命名法

```javascript
// Good
function TextNode(value, engine) {
  this.value = value;
  this.engine = engine;
}

TextNode.prototype.getClone = function () {
  return this;
};
```

- 由多个单词组成的缩写词，在命名中，根据当前命名法和出现的位置，所有字母的大小写与首字母的大小写保持一致。

```javascript
// Good
function insertHTML(element, html) {
}

var httpRequest = new HTTPRequest();
var URL = "http://...";
```


## 3. 注释


### 3.1 单行注释

- 独占一行的单行注释前要有空行。`//` 后跟一个空格，缩进层级与下一行被注释说明的代码一致
- 若单行注释在代码行尾部，注释与代码结尾至少要有一个空格，若加上注释超过 `120` 字符，则把注释写在代码行上一行
- 注释行数多不推荐使用单行注释

```javascript
// Good
if (condition) {

  // 为 a 赋值
  var a = 10;
  var URL = "http://..."; //此处不要缺省
}
```


### 3.2 多行注释

- 注释行数过少（小于 3）的时候不推荐使用 `/*...*/` 这样的多行注释，缩进层级与下一行被注释说明的代码一致。`*` 和文本之间要有一个空格

```javascript
// Good
if (condition) {

  /*
  * 为了
  * 给 a
  * 赋值
  */
  var a = 10;
}
```


### 3.3 文档注释

- 文档注释包含在 `/**...*/` 形式的注释块中。
- 文档注释前必须空一行。
- 建议使用文档注释说明 *是什么*，而非 *怎么做*。

```javascript
// Good
/**
* 更新
* @param params
* @param callback
*/
```

- 可以通过文档注释生成文档，如果你要这么做，请对 *所有方法*，*所有构造函数* 以及 *所有包含文档化方法的对象* 都添加文档注释
- 补充一些常见的文档注释关键字

|关键字|作用|
| ---- | -------------- |
|author | 标识代码作者 |
|constructor | 同class |
|default | 默认值 |
|description | 对象描述 |
|event | 事件函数 |
|example | 例子代码 |
|ignore | 忽略有这个标记的函数 |
|link | 与其他JsDoc对象关联 |
|name | 显示声明JsDoc不能自动检测的对象 |
|namespace | 声明命名空间 |
|param | 参数 |
|private | 声明私有对象 |
|property | 显式声明一个属性 |
|public | 声明公开对象 |
|requires | 声明所依赖的对象或文件 |
|returns | 返回值 |
|see | 声明可参考的其它对象 |
|since | 声明对象从指定版本开始生效 |
|static | 显式声明一个静态对象 |
|throws | 声明函数执行过程中可能抛出的异常 |
|type | 声明变量类型或者函数返回值类型 |
|version | 版本号 |


### 3.4 特殊注释

有时用一些特殊标记进行说明，请使用单行注释的格式

| 关键字 | 作用 |
| ------ | ---- |
| TODO | 有功能待实现。此时需要对将要实现的功能进行简单说明 |
| FIXME | 该处代码运行没问题，但可能由于时间赶或者其他原因，需要修正。此时需要对如何修正进行简单说明 |
| HACK | 为修正某些问题而写的不太好或者使用了某些诡异手段的代码。此时需要对思路或诡异手段进行描述 |
| XXX | 该处存在陷阱。此时需要对陷阱进行描述 |


## 4. 语言特性


### 4.1 基础数据类型


#### 4.1.1 字符串[String]

- 使用双引号将字符串括起来，当产生歧义时注意使用转义字符
- 不要使用 `\` 连接字符串，而是使用 `+` 连接字符串。

```javascript
// Bad
var str = "One page Application website designs for your \ inspiration";

// Good
var str = "One page Application website designs for your " + "inspiration";
```

#### 4.1.2 数[Number]

- 浮点数的整数部分和小数部分都不要省略
- 不建议使用八进制数

```javascript
// Bad
var price = 10.;
var price = .5;

var octal = 010;

// Good
var price = 10.0;
var price = 0.5;
```

#### 4.1.3 Null

- 不要用 null 检测是否传入了一个参数
- 不要用 null 检测一个未初始化的变量
- 可以用来初始化未来可能被申明为对象的变量
- 可以与一个可能是对象或者非对象的初始化变量比较
- 当函数参数是对象时，可以用作参数传入
- 当函数返回值是对象时，可以用作返回值返回

#### 4.1.4 Undefined

尽量避免将变量赋值为 undefined，不论变量未定义还是变量值为 undefined，typeof 都会返回 undefined。



### 4.2 引用类型

#### 4.2.1 对象[Object]

- 使用对象字面量创建对象，避免使用显示创建对象
- 对象创建时，属性名是否用引号包裹都可以，但务必统一

```javascript
// Bad
var book = new Object();
book.title = "JavaScript";
book.author = "dreamarts";

// Good
var book = {
  title: "JavaScript",
  author: "dreamarts"
};
```

- 不允许修改和扩展任何原生对象和宿主对象的原型

```javascript
// Bad
String.prototype.trim = function () {
};
```

-  属性访问时，尽量使用 `.`，少数时候也可以使用 `[]`。
-  `for..in` 遍历对象时, 推荐使用 `hasOwnProperty` 过滤掉原型中的属性。

#### 4.2.2 数组[Array]

- 如果不是创建固定长度的数组，则使用数组字面量创建数组
- 遍历数组不要使用 `for..in`，可以使用 `for` 或者 `forEach`

```javascript
// Bad
var colors = new Array("red", "green", "blue");

for (c in colors) {
  console.log(c);
}

// Good
var colors = ["red", "green", "blue"];

for (var i = 0, len = colors.length; i < len; i++) {
  console.log(c);
}
```


### 4.3 变量

- 变量在使用前必须通过 `var` 定义，否则变量将默认为全局变量
- 可以多个变量共用一个 `var`，注意缩进
- 由于变量声明提前，建议即用即声明，降低维护代价
- 不要随意使用全局变量，除非是团队内约定的

```javascript
// Bad
name = "a";

// Good
var name = "a";
var age = 20;

// Good
var name = "a",
    age = 20;
```


### 4.4 函数

- 不要在声明前调用函数，尽管存在函数声明提升（使用函数表达式没有函数声明提升）

```javascript
// Bad
doSomething(item);

function doSomething(item) {
  // do something
}

// Good
function doSomething(item) {
  // do something
}

doSomething(item);
```

- 不要把函数声明写在语句块之内；但如果使用函数表达式，这是安全的

```javascript
// Bad
if (condition) {
  function doSomethin() {
    console.log("yes");
  }
} else {
  function doSomethin() {
    console.log("no");
  }
}
```

- 立即执行函数务必使用 `()` 括起来
- 函数声明、函数表达式、函数调用中，函数名和 ( 之间不允许有空格

```javascript
// Good
var value = (function() {

// function body
  return {
    message: "Hi"
  }
}());
```

- 不推荐全局使用 `"use strict"`，除非所有文件都运行在严格模式下；可用立即执行函数包含代码段，将 `"use strict"` 置于函数第一行

```javascript
// 使用立即执行函数
(function() {
    "use strict";

    function doSomething() {
        // code
    }

    function doSomethingElse() {
        // code
    }

})();
```


### 4.5 运算符

- 不要使用 `==` 和 `!=`，而是使用 `===` 和 `!==`
- 二元运算符两侧必须有一个空格，一元运算符与操作对象之间不允许有空格


### 4.6 语句

#### 4.6.1 条件语句

- `if` / `else` / `switch` 关键字后，必须有一个空格 [可以参看1.2 空格]
- `switch` 下面的 `case` 务必缩进，结束一个分支一定要写 `break`
- `case` 的排列顺序最好是执行频率顺序
- `default` 语句省略的情况下，尽可能写明白注释

```javascript
switch (condition) {

  // fall through
  case "first":
  case "second":
    // code
    break;

  case "third":
    // code

  /* falls through */  // 添加该行注释可以让JSLint不对连续执行发出警告
  default:
    // code
}
h
```

#### 4.6.2 循环语句

- `for`/`while`/`do` 关键字后，必须有一个空格 [可以参看1.2 空格]，`do..while` 中，`while` 前要有一个空格
- `for..in` 用于遍历对象属性,使用时要使用 `hasOwnProperty` 过滤掉原型中的属性，除非对原型链遍历
- `for..in` 不要用于遍历数组
- `break`、`continue` 和 `label` 合理使用，避免调试过于困难

```javascript
for (prop in object) {

 // 注意这里一定要有 hasOwnProperty 的判断， 否则 JSLint 或者 JSHint 都会有一个 warn ！
 if (object.hasOwnProperty(prop)) {
    console.log("Property name is " + prop);
    console.log("Property value is " + object[prop]);
  }
}
```

- 对循环内多次使用的不变值，推荐在循环外用变量缓存
- 不要在循环体内写函数表达式，最好提到循环外

```javascript
// bad
for (var i = 0, len = elements.length; i < len; i++) {
  var element = elements[i];
  element.style.width = wrap.offsetWidth + 'px';
  addListener(element, 'click', function () {});
}

// good
var width = wrap.offsetWidth + 'px';

function clicker() {
  // ......
}

for (var i = 0, len = elements.length; i < len; i++) {
  var element = elements[i];
  element.style.width = width;
  addListener(element, 'click', clicker);
}
```

#### 4.6.3 with 语句

通常情况下都不要使用 `with` 语句。 


### 4.7 动态特性

- 尽量避免使用 `eval()` 函数
- 尽量避免通过 `new Function()` 执行动态代码 
- 使用 `setTimeout()` 和 `setInterval()` 不要用字符串形式，而是使用函数 
