# JavaScript 编码规范

----

### 1. 缩进

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


### 2. 空格

- 二元运算符两侧必须有一个空格，一元运算符与操作对象之间不允许有空格
- 用作代码块起始的左花括号 `{` 前必须有一个空格
- 在对象创建时，属性中的 `:` 之后必须有空格，`:` 之前不允许有空格
- `if` / `else` / `for` / `while` / `function` / `switch` / `do` / `try` / `catch` / `finally` 关键字后，必须有一个空格
- 函数声明、具名函数表达式、函数调用中，函数名和 ( 之间不允许有空格
- `,` 和 `;` 前不允许有空格
- `()` 、`[]` 和 `{}` 内紧贴括号部分不允许有空格
- 行尾不要有空格。


### 3. 行的长度与换行

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


### 4. 空行

- 函数之间
- 函数中局部变量和第一行语句之间
- 多行或单行注释之前
- 在函数内逻辑上独立的代码片段之间使用空行分隔
```javascript
// 好的写法
function total() {
  var i = 100;

  if (i < 10) {
  }
}

function add() {
}   
```


### 5. 语句

- 不要省略语句结束的分号。
- 在 `if` / `else` / `for` / `do` / `while` 语句中，即使只有一行，也不要省略 `{}`。

```javascript
// 好的写法
function total() {
  if (i < 10) {
    hello();
  }
}
```


### 6. 命名

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


### 7. 注释


