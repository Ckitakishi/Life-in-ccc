# JavaScript 编码规范


## 1. 代码格式

### 1.1 缩进

使用 2 个空格做为一个缩进层级，不允许使用 4 个空格 或 tab 字符。

```javascript
// 推荐的写法
if (a && b) {	
  for (i = 0, i < 10; i++) {	
    alert(i);	
  }	
}

// 不推荐的写法  
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
- 函数声明、具名函数表达式、函数调用中，函数名和 ( 之间不允许有空格

```javascript
if (a + b === 0 && !c) {
  allowed();
}
``` 

- 在对象创建时，属性中的 `:` 之后必须有空格，`:` 之前不允许有空格
- `,` 和 `;` 前不允许有空格
- 多数情况下`()` 、`[]` 和 `{}` 内紧贴括号部分不允许有空格（换行不算空格）
- 行尾不要有空格。

```javascript
var obj = {
  a: 1,
  b: 2
};
var obj2 = {c: 3};
``` 


### 1.3 行的长度与换行

- 每行不得超过 `120` 个字符(正则表达式例外)，超过务必换行。
- 通常在运算符后面换行，下一行增加两个层级（该规范指4个空格）的缩进；例外的是，给变量赋值的时候，第二行位置应当和赋值运算符位置保持对齐。
- 每个独立语句结束后换行。

```javascript
// 不好的写法
callAFunction(document, element, window, "some string value", true, 123,
  navigator);

callAFunction(document, element, window, "some string value", true, 123
    , navigator);
    
var html = "<pThe sum of " + a + " and " + b + " plus " + c
    + " is " + (a + b + c);

// 好的写法         
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
function total() {
  var i = 100;

  if (i < 10) {
  }
}

function add() {
}   
```


### 1.5 语句

- 不要省略语句结束的分号。
- 在 `if` / `else` / `for` / `do` / `while` 语句中，即使只有一行，也不要省略 `{}`。

```javascript
function total() {
  if (i < 10) {
    hello();
  }
}
```


## 2 命名

- 变量名应当遵守 `Camel` 命名法，并且命名前缀应当是名词

```javascript
var count = 10;
var myName = "c";
```

- 函数命名应当遵守 `Camel` 命名法，命名前缀应当是动词

```javascript
var count = 10;
var myName = "c";
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
var MAX_COUNT = 10;
var URL = "http://";
```

- 构造函数命名使用 `Pascal` 命名法，由于用来创建实例，所以一般是名词。
- 构造函数的方法和属性使用 `Camel` 命名法

```javascript
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
function insertHTML(element, html) {
}

var httpRequest = new HTTPRequest();
```


## 3. 注释

### 3.1 单行注释

- 独占一行的单行注释前要有空行。`//` 后跟一个空格，缩进层级与下一行被注释说明的代码一致
- 若单行注释在代码行尾部，注释与代码结尾至少要有一个空格，若加上注释超过 `120` 字符，则把注释写在代码行上一行
- 注释行数多不推荐使用单行注释

```javascript
if (condition) {

  // 为 a 赋值
  var a = 10;
  var URL = "http://..."; //此处不要缺省
}
```

### 3.2 多行注释

- 注释行数过少（小于 3）的时候不推荐使用 `/*...*/` 这样的多行注释，缩进层级与下一行被注释说明的代码一致。`*` 和文本之间要有一个空格

```javascript
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


## 4. 语言特征

### 4.1 基础数据类型

#### 4.1.1 字符串[String]

- 使用双引号将字符串括起来，当产生歧义时注意使用转义字符
- 不要使用 `\` 连接字符串，而是使用 `+` 连接字符串。

```javascript
// 不好的写法
var str = "One page Application website designs for your \ inspiration";

// 好的写法
var str = "One page Application website designs for your " + "inspiration";
```

#### 4.1.2 数[Number]

- 浮点数的整数部分和小数部分都不要省略
- 不建议使用八进制数

```javascript
// 不好的写法
var price = 10.;
var price = .5;

var octal = 010;

// 好的写法
var price = 10.0;
var price = 0.5;
```

#### 4.1.3 Null

- 不要用 null 检测是否传入了一个参数
- 不要用 null 检测一个未初始化的变量
- 可以用来初始化对象，和初始化的对象比较
- 当函数参数是对象时，可以用作参数传入
- 当函数返回值是对象时，可以用作返回值返回

#### 4.1.4 Undefined

 尽量避免将变量赋值为 undefined，不论变量未定义还是变量值为 undefined，typeof 都会返回 undefined。


### 4.2 引用类型
 
#### 4.2.1 对象[Object]
 
- 使用对象字面量创建对象，避免使用显示创建对象
- 对象创建时，属性名是否用引号包裹都可以，但务必统一

```javascript
 // 不好的写法
var book = new Object();
book.title = "JavaScript";
book.author = "dreamarts";

// 好的写法
var book = {
  title: "JavaScript",
  author: "dreamarts"
};
```

- 不允许修改和扩展任何原生对象和宿主对象的原型

```javascript
// 不可以
String.prototype.trim = function () {
};
```

-  属性访问时，尽量使用 `.`，少数时候也可以使用 `[]`。
-  `for..in` 遍历对象时, 推荐使用 `hasOwnProperty` 过滤掉原型中的属性。

#### 4.2.2 数组[Array]

- 如果不是创建固定长度的数组，则使用数组字面量创建数组 
- 遍历数组不要使用 `for..in`，可以使用 `for` 或者 `forEach`

```javascript
// 不好的写法
var colors = new Array("red", "green", "blue");

for (c in colors) {
    console.log(c);
}

// 好的写法
var colors = ["red", "green", "blue"];

for (var i = 0, len = colors.length; i < len; i++) {
    console.log(c);
}
```

### 4.3 变量

- 变量在使用前必须通过 `var` 定义，否则变量将默认为全局变量
- 可以多个变量共用一个 `var`，注意缩进
- 由于变量声明提前，建议即用即声明，降低维护代价

```javascript
// 不好的写法
name = "a"; 

// 都可以
var name = "a";
var age = 20;

var name = "a",
    age = 20;
```

### 4.4 函数


### 4.5 运算符

