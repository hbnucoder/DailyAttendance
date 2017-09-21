作为一个前端开发人员，遵守一定的编码规范是很有必要的，因此我这里总结了一些规范作为自己日后开发的编码规范，当然，在实际的工作中要优先遵守公司制定的规范，确保跟团队其他人写的代码风格上是一样的，这样有利于日后的维护。 
下面总结了一些基本的编码规范，包括通用规范、html规范、css规范以及ES6规范四个方面
# 通用规范

---

## 基本准则

- 保证开发的有效性和合理性，并可最大程度的提高程序代码的可读性和可重复利用性。

- 符合web标准, 语义化html, 结构表现行为分离, 兼容性优良. 页面性能方面, 代码要求简洁明了有序, 尽可能的减小服务器负载, 保证最快的解析速度。

- 不管有多少人共同参与同一项目，尽量确保每一行代码都像是同一个人编写的。

## 编码

文件统一使用utf-8编码   



## 优雅降级和渐进增强

HTML5 和 CSS3 的快速发展，给我们带来了极大的便利，比如从此再也不用花费大量的时间只是为了设计一个圆角的效果。

但是我们不能像控制机器一样来控制所有的人都一夜之间升级到现代浏览器，因为那些 不够现代的浏览器 诞生之时，HTML5和CSS3尚未被正式推出。

于是，我们的问题来了：针对那些不支持新特性的浏览器而言，我们是直接放弃这些用户群呢，还是直接不用这些新特性，老老实实的用图片拼出圆角的特效？

在保证基础功能不受影响的基础上，应多尝试使用新技术！




## 代码检查/验证工具

为符合 W3C 标准及 SEO 优化，我们在遵守本手册规范的基本之上，上线的网站都要使用以下工具来检查代码，虽说优化没有100分，但我们要尽量符合要求
- 使用 [W3C Markup Validation Service](https://validator.w3.org/) 验证html规范
- 使用 [CSS Validation Service](http://jigsaw.w3.org/css-validator/) 验证css规范
---

# CSS规范
--- 

## 基本
  - class 名称中只能出现小写字符和中划线（不再使用驼峰和下划线）。破折号应当用于相关 class 的命名（类似于命名空间）（例如，.btn 和 .btn-danger）
    - 避免过度任意的简写。.btn 代表 button，但是 .s 不能表达任何意思,永远不要使用单个单词命名类
    - class 名称应当尽可能短，并且意义明确
    - 基于最近的父 class[模块常见] 或基本（base） class 作为新 class 的前缀[组件常见] 例如:.main .hd， .panel-default ,.btn-m  
    - 永远不要使用原子类,过多依赖原子类会直接导致页面样式难以维护,例如:.fs10,.fs20,.pd20,.pd30
    - 通过.j-option操作节点，不应和样式class挂钩



##命名
1通用命名规则：
 .-禁止"模块内"的样式污染全局模块  禁止: .bd      应:.mian .bd
 .-

2.常见“模块”以及命名:

主  体：main
外　层：wrap
功能条：funcBar
主导航：mainNav
子导航：subNav
友情链接：friendLink
版  权：copyright
页　眉：header
页　脚：footer
标　题：title
主导航：mainNav
子菜单：subMenu
注  释：note
面包屑：breadcrumb

容  器：container
内  容：content
搜  索：search
登  陆：Login
当前状态：current

页头：header
标志：logo
侧栏：sidebar
广告：banner
导航：nav
子导航：subnav
菜单：menu
子菜单：submenu
搜索：search
滚动：scroll
页面主体：main
内容：content
标签页：tab
文章列表：list

信息：msg
提示技巧：tips
栏目标题：title
指南：guide
服务：service
热点：hot
新闻：news
下载：download
注册：reg（register）
状态：status
按钮：btn
投票：vote

3.常用简写命名规则：
bd：Body   例如:.panel-bd
hd：Header  例如:.panel-hd
fnt：字体 
nav：导航   
ml/mr：margin-left/margin-right 
lst：列表 
pl / pr / pd：padding-left/-right/padding 
col：栏目 
inf：信息 
lg：Logo 
btn：Button 
more：更多 
fl /fr float:left/float:right 
tit 标题栏 


## 声明顺序
相关的属性声明应当归为一组，并按照下面的顺序排列:

- 位置属性(position, top, right, z-index)

- 盒模型（display, float等）

- 大小(width, height, padding, margin)

- 文字系列(font, line-height, letter-spacing, color， text-align等)

- 背景，修饰(background, border等)

- 其他效果(animation, transition等)

```css
.declaration-order {
  /* 位置属性 */
  position: absolute;top: 0;right: 0;bottom: 0;left: 0;z-index: 100;
  
  /* 盒模型 */
  display: block;float: right;width: 100px;height: 100px;

  /* 文字系列*/
  font: normal 13px "Helvetica Neue", sans-serif;line-height: 1.5;color: #333;text-align: center;

  /* 背景，修饰 */
  background-color: #f5f5f5;border: 1px solid #e5e5e5;border-radius: 3px;

  /* 其它效果 */
  opacity: 1;transition: all 500ms;
}
```



## 媒体查询
将媒体查询放在尽可能相关规则的附近。不要将他们打包放在一个单一样式文件中或者放在文档底部。如果你把他们分开了，将来只会被大家遗忘。下面给出一个典型的实例。
```css
.element { ... }
.element-avatar { ... }
.element-selected { ... }

@media (min-width: 480px) {
  .element { ...}
  .element-avatar { ... }
  .element-selected { ... }
}
```


## 简写形式的属性声明
在需要显示地设置所有值的情况下，应当尽量限制使用简写形式的属性声明。常见的滥用简写属性声明的情况如下：
- padding
- margin
- font
- background
- border
- border-radius 

大部分情况下，我们不需要为简写形式的属性声明指定所有值。例如，HTML 的 heading 元素只需要设置上、下边距（margin）的值，因此，在必要的时候，只需覆盖这两个值就可以。过度使用简写形式的属性声明会导致代码混乱，并且会对属性值带来不必要的覆盖从而引起意外的副作用。

```css
/* Bad */
.element {
  margin: 0 0 10px;
  background: red;
  background: url("image.jpg");
  border-radius: 3px 3px 0 0;
}

/* Good */
.element {
  margin-bottom: 10px;
  background-color: red;
  background-image: url("image.jpg");
  border-top-left-radius: 3px;
  border-top-right-radius: 3px;
}
```
扩展阅读： [CSS 的简写属性 - CSS | MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Shorthand_properties)


## 清除浮动

当元素需要撑起高度以包含内部的浮动元素时统一使用 [clearfix]方案
```css
.clearfix:after { 
  display: block; 
  content: ""; 
  clear: both; 
  *zoom: 1; 
} 
```


## 参考资料

- [http://codeguide.bootcss.com/#css-media-queries](http://codeguide.bootcss.com/#css-media-queries)

# ES6 Style Guide

**用更合理的方式写 JavaScript**

翻译自 [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript) 。 [翻译原文地址](https://github.com/yuche/javascript) 

> 因为自己团队用删减部分见谅 如有需要，请看原版
>
> 团队代码缩进为2个空格，行末不加分号，不作为讨论范围 

<a name="table-of-contents"></a>
## 目录

  1. [类型](#types)
  2. [引用](#references)
  3. [对象](#objects)
  4. [数组](#arrays)
  5. [解构](#destructuring)
  6. [字符串](#strings)
  7. [函数](#functions)
  8. [箭头函数](#arrow-functions)
  9. [构造函数](#constructors)
  10. [模块](#modules)
  11. [Iterators & Generators ](#iterators-and-generators)
  12. [属性](#properties)
  13. [变量](#variables)
  14. [提升](#hoisting)
  15. [比较运算符 & 等号](#comparison-operators--equality)
  16. [代码块](#blocks)
  17. [注释](#comments)
  18. [空白](#whitespace)
  19. [逗号](#commas)
  20. [分号](#semicolons)
  21. [类型转换](#type-casting--coercion)
  22. [命名规则](#naming-conventions)
  23. [存取器](#accessors)
  24. [事件](#events)
  25. [jQuery](#jquery)
 

      ​

<a name="types"></a>
##  类型 

- [1.1](#1.1) <a name='1.1'></a> **基本类型**: 直接存取基本类型。

  + `字符串`
  + `数值`
  + `布尔类型`
  + `null`
  + `undefined`

  ```javascript
  const foo = 1
  let bar = foo

  bar = 9

  console.log(foo, bar) // => 1, 9
  ```
- [1.2](#1.2) <a name='1.2'></a> **复制类型**: 通过引用的方式存取复杂类型。

  + `对象`
  + `数组`
  + `函数`

  ```javascript
  const foo = [1, 2]
  const bar = foo

  bar[0] = 9

  console.log(foo[0], bar[0]) // => 9, 9
  ```

**[⬆ 返回目录](#table-of-contents)**

<a name="references"></a>
## 引用

- [2.1](#2.1) <a name='2.1'></a> 对所有的引用使用 `const` ；不要使用 `var`。

  > 为什么？这能确保你无法对引用重新赋值，也不会导致出现 bug 或难以理解。

```javascript
// bad
var a = 1
var b = 2

// good
const a = 1
const b = 2
```

- [2.2](#2.2) <a name='2.2'></a> 如果你一定需要可变动的引用，使用 `let` 代替 `var`。

  > 为什么？因为  `let` 是块级作用域，而 `var` 是函数作用域。

```javascript
// bad
var count = 1
if (true) {
  count += 1
}

// good, use the let.
let count = 1
if (true) {
  count += 1
}
```

- [2.3](#2.3) <a name='2.3'></a> 注意 `let` 和 `const` 都是块级作用域。

  ```javascript
  // const 和 let 只存在于它们被定义的区块内。
  {
    let a = 1
    const b = 1
  }
  console.log(a) // ReferenceError
  console.log(b) // ReferenceError
  ```

**[⬆ 返回目录](#table-of-contents)**

<a name="objects"></a>
## 对象

- [3.1](#3.1) <a name='3.1'></a> 使用字面值创建对象。

  ```javascript
  // bad
  const item = new Object();

  // good
  const item = {};
  ```

- [3.2](#3.2) <a name='3.2'></a> 如果你的代码在浏览器环境下执行，别使用 [保留字](http://es5.github.io/#x7.6.1) 作为键值。这样的话在 IE8 不会运行。 [更多信息](https://github.com/airbnb/javascript/issues/61)。 但在 ES6 模块和服务器端中使用没有问题。

  ```javascript
  // bad
  const superman = {
    default: { clark: 'kent' },
    private: true
  }

  // good
  const superman = {
    defaults: { clark: 'kent' },
    hidden: true
  }
  ```

- [3.3](#3.3) <a name='3.3'></a> 使用同义词替换需要使用的保留字。

  ```javascript
  // bad
  const superman = {
    class: 'alien',
  }

  // bad
  const superman = {
    klass: 'alien',
  }

  // good
  const superman = {
    type: 'alien',
  }
  ```

  <a name="es6-computed-properties"></a>
- [3.4](#3.4) <a name='3.4'></a> 创建有动态属性名的对象时，使用可被计算的属性名称。

  > 为什么？因为这样可以让你在一个地方定义所有的对象属性。

```javascript

function getKey(k) {
  return `a key named ${k}`
}

// bad
const obj = {
  id: 5,
  name: 'San Francisco'
}
obj[getKey('enabled')] = true

// good
const obj = {
  id: 5,
  name: 'San Francisco',
  [getKey('enabled')]: true
}

```

  <a name="es6-object-shorthand"></a>
- [3.5](#3.5) <a name='3.5'></a> 使用对象方法的简写。

  ```javascript
  // bad
  const atom = {
    value: 1,
    addValue: function (value) {
      return atom.value + value
    }
  };

  // good
  const atom = {
    value: 1,
    addValue(value) {
      return atom.value + value
    },
  }
  ```

  <a name="es6-object-concise"></a>
- [3.6](#3.6) <a name='3.6'></a> 使用对象属性值的简写。

  > 为什么？因为这样更短更有描述性。

```javascript
const lukeSkywalker = 'Luke Skywalker'

// bad
const obj = {
  lukeSkywalker: lukeSkywalker,
}

// good
const obj = {
  lukeSkywalker
}
```

- [3.7](#3.7) <a name='3.7'></a> 在对象属性声明前把简写的属性分组。

  > 为什么？因为这样能清楚地看出哪些属性使用了简写。

```javascript
const anakinSkywalker = 'Anakin Skywalker'
const lukeSkywalker = 'Luke Skywalker'

// bad
const obj = {
  episodeOne: 1,
  twoJedisWalkIntoACantina: 2,
  lukeSkywalker,
  episodeThree: 3,
  mayTheFourth: 4,
  anakinSkywalker
}

// good
const obj = {
  lukeSkywalker,
  anakinSkywalker,
  episodeOne: 1,
  twoJedisWalkIntoACantina: 2,
  episodeThree: 3,
  mayTheFourth: 4
}
```

**[⬆ 返回目录](#table-of-contents)**

<a name="arrays"></a>
## 数组

- [4.1](#4.1) <a name='4.1'></a> 使用字面值创建数组。

  ```javascript
  // bad
  const items = new Array();

  // good
  const items = [];
  ```

- [4.2](#4.2) <a name='4.2'></a> 向数组添加元素时使用 Arrary#push 替代直接赋值。

  ```javascript
  const someStack = []
  // bad
  someStack[someStack.length] = 'abracadabra'

  // good
  someStack.push('abracadabra')
  ```




  <a name="es6-array-spreads"></a>
- [4.3](#4.3) <a name='4.3'></a> 使用拓展运算符 `...` 复制数组。

  ```javascript
  // bad
  const len = items.length
  const itemsCopy = []
  let i

  for (i = 0; i < len; i++) {
    itemsCopy[i] = items[i]
  }

  // good
  const itemsCopy = [...items]
  ```
- [4.4](#4.4) <a name='4.4'></a> 使用 Array#from 把一个类数组对象转换成数组。

  ```javascript
  const foo = document.querySelectorAll('.foo')
  const nodes = Array.from(foo)
  ```

**[⬆ 返回目录](#table-of-contents)**

<a name="destructuring"></a>
## 解构

- [5.1](#5.1) <a name='5.1'></a> 使用解构存取和使用多属性对象。

  > 为什么？因为解构能减少临时引用属性。

```javascript
// bad
function getFullName(user) {
  const firstName = user.firstName
  const lastName = user.lastName

  return `${firstName} ${lastName}`
}

// good
function getFullName(obj) {
  const { firstName, lastName } = obj
  return `${firstName} ${lastName}`
}

// best
function getFullName({ firstName, lastName }) {
  return `${firstName} ${lastName}`
}
```

- [5.2](#5.2) <a name='5.2'></a> 对数组使用解构赋值。

  ```javascript
  const arr = [1, 2, 3, 4]

  // bad
  const first = arr[0]
  const second = arr[1]

  // good
  const [first, second] = arr
  ```

- [5.3](#5.3) <a name='5.3'></a> 需要回传多个值时，使用对象解构，而不是数组解构。
  > 为什么？增加属性或者改变排序不会改变调用时的位置。

```javascript
// bad
function processInput(input) {
  // then a miracle occurs
  return [left, right, top, bottom];
}

// 调用时需要考虑回调数据的顺序。
const [left, __, top] = processInput(input);

// good
function processInput(input) {
  // then a miracle occurs
  return { left, right, top, bottom };
}

// 调用时只选择需要的数据
const { left, right } = processInput(input);
```


**[⬆ 返回目录](#table-of-contents)**

<a name="strings"></a>
## Strings

- [6.1](#6.1) <a name='6.1'></a> 字符串使用单引号 `''` 。

  ```javascript
  // bad
  const name = "Capt. Janeway"

  // good
  const name = 'Capt. Janeway'
  ```

- [6.2](#6.2) <a name='6.2'></a> 字符串超过 80 个字节应该使用字符串连接号换行。
- [6.3](#6.3) <a name='6.3'></a> 注：过度使用字串连接符号可能会对性能造成影响。[jsPerf](http://jsperf.com/ya-string-concat) 和 [讨论](https://github.com/airbnb/javascript/issues/40).

  ```javascript
  // bad
  const errorMessage = 'This is a super long error that was thrown because of Batman. When you stop to think about how Batman had anything to do with this, you would get nowhere fast.'

  // bad
  const errorMessage = 'This is a super long error that was thrown because \
  of Batman. When you stop to think about how Batman had anything to do \
  with this, you would get nowhere \
  fast.'

  // good
  const errorMessage = 'This is a super long error that was thrown because ' +
    'of Batman. When you stop to think about how Batman had anything to do ' +
    'with this, you would get nowhere fast.'
  ```

  <a name="es6-template-literals"></a>
- [6.4](#6.4) <a name='6.4'></a> 程序化生成字符串时，使用模板字符串代替字符串连接。

  > 为什么？模板字符串更为简洁，更具可读性。

```javascript
// bad
function sayHi(name) {
  return 'How are you, ' + name + '?';
}

// bad
function sayHi(name) {
  return ['How are you, ', name, '?'].join();
}

// good
function sayHi(name) {
  return `How are you, ${name}?`;
}
```

**[⬆ 返回目录](#table-of-contents)**

<a name="functions"></a>
## 函数

- [7.1](#7.1) <a name='7.1'></a> 使用函数声明代替函数表达式。

  > 为什么？因为函数声明是可命名的，所以他们在调用栈中更容易被识别。此外，函数声明会把整个函数提升（hoisted），而函数表达式只会把函数的引用变量名提升。这条规则使得[箭头函数](#arrow-functions)可以取代函数表达式。

```javascript
// bad
const foo = function () {
};

// good
function foo() {
}
```

- [7.2](#7.2) <a name='7.2'></a> 函数表达式:

  ```javascript
  // 立即调用的函数表达式 (IIFE)
  (() => {
    console.log('Welcome to the Internet. Please follow me.');
  })();
  ```

- [7.3](#7.3) <a name='7.3'></a>  **注意:**永远不要在一个非函数代码块（`if`、`while` 等）中声明一个函数，把那个函数赋给一个变量。浏览器允许你这么做，但它们的解析表现不一致。
- [7.4](#7.4) <a name='7.4'></a> **注意:** ECMA-262 把 `block` 定义为一组语句。函数声明不是语句。[阅读 ECMA-262 关于这个问题的说明](http://www.ecma-international.org/publications/files/ECMA-ST/Ecma-262.pdf#page=97)。

  ```javascript
  // bad
  if (currentUser) {
    function test() {
      console.log('Nope.');
    }
  }

  // good
  let test;
  if (currentUser) {
    test = () => {
      console.log('Yup.');
    };
  }
  ```

- [7.5](#7.5) <a name='7.5'></a> 永远不要把参数命名为 `arguments`。这将取代原来函数作用域内的 `arguments` 对象。

  ```javascript
  // bad
  function nope(name, options, arguments) {
    // ...stuff...
  }

  // good
  function yup(name, options, args) {
    // ...stuff...
  }
  ```

  <a name="es6-rest"></a>
- [7.6](#7.6) <a name='7.6'></a> 不要使用 `arguments`。可以选择 rest 语法 `...` 替代。

  > 为什么？使用 `...` 能明确你要传入的参数。另外 rest 参数是一个真正的数组，而 `arguments` 是一个类数组。

```javascript
// bad
function concatenateAll() {
  const args = Array.prototype.slice.call(arguments);
  return args.join('')
}

// good
function concatenateAll(...args) {
  return args.join('')
}
```

  <a name="es6-default-parameters"></a>
- [7.7](#7.7) <a name='7.7'></a> 直接给函数的参数指定默认值，不要使用一个变化的函数参数。

  ```javascript
  // really bad
  function handleThings(opts) {
    // 不！我们不应该改变函数参数。
    // 更加糟糕: 如果参数 opts 是 false 的话，它就会被设定为一个对象。
    // 但这样的写法会造成一些 Bugs。
    //（译注：例如当 opts 被赋值为空字符串，opts 仍然会被下一行代码设定为一个空对象。）
    opts = opts || {};
    // ...
  }

  // still bad
  function handleThings(opts) {
    if (opts === void 0) {
      opts = {};
    }
    // ...
  }

  // good
  function handleThings(opts = {}) {
    // ...
  }
  ```

- [7.8](#7.8) <a name='7.8'></a> 直接给函数参数赋值时需要避免副作用。

  > 为什么？因为这样的写法让人感到很困惑。

```javascript
  var b = 1;
  // bad
  function count(a = b++) {
    console.log(a);
  }
  count();  // 1
  count();  // 2
  count(3); // 3
  count();  // 3
```


**[⬆ 返回目录](#table-of-contents)**

<a name="arrow-functions"></a>
## 箭头函数

- [8.1](#8.1) <a name='8.1'></a> 当你必须使用函数表达式（或传递一个匿名函数）时，使用箭头函数符号。

  > 为什么?因为箭头函数创造了新的一个 `this` 执行环境（译注：参考 [Arrow functions - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) 和 [ES6 arrow functions, syntax and lexical scoping](http://toddmotto.com/es6-arrow-functions-syntaxes-and-lexical-scoping/)），通常情况下都能满足你的需求，而且这样的写法更为简洁。


  > 为什么不？如果你有一个相当复杂的函数，你或许可以把逻辑部分转移到一个函数声明上。

```javascript
// bad
[1, 2, 3].map(function (x) {
  return x * x
})

// good
[1, 2, 3].map((x) => {
  return x * x
})
```

- [8.2](#8.2) <a name='8.2'></a> 如果一个函数适合用一行写出并且只有一个参数，那就把花括号、圆括号和 `return` 都省略掉。如果不是，那就不要省略。

  > 为什么？语法糖。在链式调用中可读性很高。


  > 为什么不？当你打算回传一个对象的时候。

```javascript
// good
[1, 2, 3].map(x => x * x)

// good
[1, 2, 3].reduce((total, n) => {
  return total + n
}, 0)
```

**[⬆ 返回目录](#table-of-contents)**

<a name="constructors"></a>
## 构造器

- [9.1](#9.1) <a name='9.1'></a> 总是使用 `class`。避免直接操作 `prototype` 。

  > 为什么? 因为 `class` 语法更为简洁更易读。

```javascript
// bad
function Queue(contents = []) {
  this._queue = [...contents]
}
Queue.prototype.pop = function() {
  const value = this._queue[0]
  this._queue.splice(0, 1)
  return value
}
// good
class Queue {
  constructor(contents = []) {
    this._queue = [...contents]
  }
  pop() {
    const value = this._queue[0]
    this._queue.splice(0, 1)
    return value
  }
}
```

- [9.2](#9.2) <a name='9.2'></a> 使用 `extends` 继承。

  > 为什么？因为 `extends` 是一个内建的原型继承方法并且不会破坏 `instanceof`。

```javascript

// bad
const inherits = require('inherits')
function PeekableQueue(contents) {
  Queue.apply(this, contents)
}
inherits(PeekableQueue, Queue)
PeekableQueue.prototype.peek = function() {
  return this._queue[0]
}

// good
class PeekableQueue extends Queue {
  peek() {
    return this._queue[0];
  }
}
```

- [9.3](#9.3) <a name='9.3'></a> 方法可以返回 `this` 来帮助链式调用。

  ```javascript
  // bad
  Jedi.prototype.jump = function() {
    this.jumping = true
    return true
  };

  Jedi.prototype.setHeight = function(height) {
    this.height = height;
  };

  const luke = new Jedi()
  luke.jump() // => true
  luke.setHeight(20) // => undefined

  // good
  class Jedi {
    jump() {
      this.jumping = true
      return this
    }

    setHeight(height) {
      this.height = height
      return this
    }
  }

  const luke = new Jedi()

  luke.jump().setHeight(20)
  ```


- [9.4](#9.4) <a name='9.4'></a> 可以写一个自定义的 `toString()` 方法，但要确保它能正常运行并且不会引起副作用。

  ```javascript
  class Jedi {
    constructor(options = {}) {
      this.name = options.name || 'no name'
    }

    getName() {
      return this.name;
    }

    toString() {
      return `Jedi - ${this.getName()}`
    }
  }
  ```

**[⬆ 返回目录](#table-of-contents)**

<a name="modules"></a>
## 模块

- [10.1](#10.1) <a name='10.1'></a> 总是使用模组 (`import`/`export`) 而不是其他非标准模块系统。你可以编译为你喜欢的模块系统。

  > 为什么？模块就是未来，让我们开始迈向未来吧。

```javascript
// bad
const AirbnbStyleGuide = require('./AirbnbStyleGuide')
module.exports = AirbnbStyleGuide.es6

// ok
import AirbnbStyleGuide from './AirbnbStyleGuide'
export default AirbnbStyleGuide.es6

// best
import { es6 } from './AirbnbStyleGuide'
export default es6
```

- [10.2](#10.2) <a name='10.2'></a> 不要使用通配符 import。

  > 为什么？这样能确保你只有一个默认 export。

```javascript
// bad
import * as AirbnbStyleGuide from './AirbnbStyleGuide'

// good
import AirbnbStyleGuide from './AirbnbStyleGuide'
```

- [10.3](#10.3) <a name='10.3'></a>不要从 import 中直接 export。

  > 为什么？虽然一行代码简洁明了，但让 import 和 export 各司其职让事情能保持一致。

```javascript
// bad
// filename es6.js
export { es6 as default } from './airbnbStyleGuide'

// good
// filename es6.js
import { es6 } from './AirbnbStyleGuide'
export default es6
```

**[⬆ 返回目录](#table-of-contents)**

<a name="iterators-and-generators"></a>
## Iterators and Generators

- [11.1](#11.1) <a name='11.1'></a> 不要使用 iterators。使用高阶函数例如 `map()` 和 `reduce()` 替代 `for-of`。

  > 为什么？这加强了我们不变的规则。处理纯函数的回调值更易读，这比它带来的副作用更重要。

```javascript
const numbers = [1, 2, 3, 4, 5]

// bad
let sum = 0
for (let num of numbers) {
  sum += num
}

sum === 15

// good
let sum = 0
numbers.forEach((num) => sum += num)
sum === 15

// best (use the functional force)
const sum = numbers.reduce((total, num) => total + num, 0)
sum === 15
```

- [11.2](#11.2) <a name='11.2'></a> 现在还不要使用 generators。

  > 为什么？因为它们现在还没法很好地编译到 ES5。 (译者注：目前(2016/03) Chrome 和 Node.js 的稳定版本都已支持 generators)

**[⬆ 返回目录](#table-of-contents)**

<a name="properties"></a>
## 属性

- [12.1](#12.1) <a name='12.1'></a> 使用 `.` 来访问对象的属性。

  ```javascript
  const luke = {
    jedi: true,
    age: 28
  }

  // bad
  const isJedi = luke['jedi']

  // good
  const isJedi = luke.jedi
  ```

- [12.2](#12.2) <a name='12.2'></a> 当通过变量访问属性时使用中括号 `[]`。

  ```javascript
  const luke = {
    jedi: true,
    age: 28
  };

  function getProp(prop) {
    return luke[prop]
  }

  const isJedi = getProp('jedi')
  ```

**[⬆ 返回目录](#table-of-contents)**

<a name="variables"></a>
## 变量

- [13.1](#13.1) <a name='13.1'></a> 一直使用 `const` 来声明变量，如果不这样做就会产生全局变量。我们需要避免全局命名空间的污染。[地球队长](http://www.wikiwand.com/en/Captain_Planet)已经警告过我们了。（译注：全局，global 亦有全球的意思。地球队长的责任是保卫地球环境，所以他警告我们不要造成「全球」污染。）

  ```javascript
  // bad
  superPower = new SuperPower();

  // good
  const superPower = new SuperPower();
  ```

- [13.2](#13.2) <a name='13.2'></a> 使用 `const` 声明每一个变量。

  > 为什么？增加新变量将变的更加容易，而且你永远不用再担心调换错 `;` 跟 `,`。

  ```javascript
  // bad
  const items = getItems(),
      goSportsTeam = true,
      dragonball = 'z'

  // bad
  // (compare to above, and try to spot the mistake)
  const items = getItems(),
      goSportsTeam = true
      dragonball = 'z'

  // good
  const items = getItems()
  const goSportsTeam = true
  const dragonball = 'z'
  ```

- [13.3](#13.3) <a name='13.3'></a> 将所有的 `const` 和 `let` 分组

  > 为什么？当你需要把已赋值变量赋值给未赋值变量时非常有用。

```javascript
// bad
let i, len, dragonball,
    items = getItems(),
    goSportsTeam = true

// bad
let i;
const items = getItems()
let dragonball
const goSportsTeam = true
let len

// good
const goSportsTeam = true
const items = getItems()
let dragonball
let i
let length
```

- [13.4](#13.4) <a name='13.4'></a> 在你需要的地方给变量赋值，但请把它们放在一个合理的位置。

  > 为什么？`let` 和 `const` 是块级作用域而不是函数作用域。

```javascript
// good
function() {
  test();
  console.log('doing stuff..');

  //..other stuff..

  const name = getName();

  if (name === 'test') {
    return false;
  }

  return name;
}

// bad - unnecessary function call
function(hasName) {
  const name = getName();

  if (!hasName) {
    return false;
  }

  this.setFirstName(name);

  return true;
}

// good
function(hasName) {
  if (!hasName) {
    return false;
  }

  const name = getName();
  this.setFirstName(name);

  return true;
}
```

**[⬆ 返回目录](#table-of-contents)**

<a name="hoisting"></a>
## Hoisting

- [14.1](#14.1) <a name='14.1'></a> `var` 声明会被提升至该作用域的顶部，但它们赋值不会提升。`let` 和 `const` 被赋予了一种称为「[暂时性死区（Temporal Dead Zones, TDZ）](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#Temporal_dead_zone_and_errors_with_let)」的概念。这对于了解为什么 [type of 不再安全](http://es-discourse.com/t/why-typeof-is-no-longer-safe/15)相当重要。

  ```javascript
  // 我们知道这样运行不了 
  // （假设 notDefined 不是全局变量）
  function example() {
    console.log(notDefined) // => throws a ReferenceError
  }

  // 由于变量提升的原因，
  // 在引用变量后再声明变量是可以运行的。
  // 注：变量的赋值 `true` 不会被提升。
  function example() {
    console.log(declaredButNotAssigned) // => undefined
    var declaredButNotAssigned = true
  }

  // 编译器会把函数声明提升到作用域的顶层，
  // 这意味着我们的例子可以改写成这样：
  function example() {
    let declaredButNotAssigned
    console.log(declaredButNotAssigned) // => undefined
    declaredButNotAssigned = true
  }

  // 使用 const 和 let
  function example() {
    console.log(declaredButNotAssigned) // => throws a ReferenceError
    console.log(typeof declaredButNotAssigned) // => throws a ReferenceError
    const declaredButNotAssigned = true
  }
  ```

- [14.2](#14.2) <a name='14.2'></a> 匿名函数表达式的变量名会被提升，但函数内容并不会。

  ```javascript
  function example() {
    console.log(anonymous) // => undefined

    anonymous() // => TypeError anonymous is not a function

    var anonymous = function() {
      console.log('anonymous function expression')
    }
  }
  ```

- [14.3](#14.3) <a name='14.3'></a> 命名的函数表达式的变量名会被提升，但函数名和函数函数内容并不会。

  ```javascript
  function example() {
    console.log(named) // => undefined
    named() // => TypeError named is not a function
    superPower() // => ReferenceError superPower is not defined
    var named = function superPower() {
      console.log('Flying');
    };
  }

  // the same is true when the function name
  // is the same as the variable name.
  function example() {
    console.log(named); // => undefined
    named(); // => TypeError named is not a function
    var named = function named() {
      console.log('named');
    }
  }
  ```

- [14.4](#14.4) <a name='14.4'></a> 函数声明的名称和函数体都会被提升。

  ```javascript
  function example() {
    superPower(); // => Flying
    
    function superPower() {
      console.log('Flying')
    }
  }
  ```

- 想了解更多信息，参考 [Ben Cherry](http://www.adequatelygood.com/) 的 [JavaScript Scoping & Hoisting](http://www.adequatelygood.com/2010/2/JavaScript-Scoping-and-Hoisting)。

**[⬆ 返回目录](#table-of-contents)**

<a name="comparison-operators--equality"></a>
## 比较运算符 & 等号

- [15.1](#15.1) <a name='15.1'></a> 优先使用 `===` 和 `!==` 而不是 `==` 和 `!=`.
- [15.2](#15.2) <a name='15.2'></a> 条件表达式例如 `if` 语句通过抽象方法 `ToBoolean` 强制计算它们的表达式并且总是遵守下面的规则：

  + **对象** 被计算为 **true**
  + **Undefined** 被计算为 **false**
  + **Null** 被计算为 **false**
  + **布尔值** 被计算为 **布尔的值**
  + **数字** 如果是 **+0、-0、或 NaN** 被计算为 **false**, 否则为 **true**
  + **字符串** 如果是空字符串 `''` 被计算为 **false**，否则为 **true**

  ```javascript
  if ([0]) {
    // true
    // An array is an object, objects evaluate to true
  }
  ```

- [15.3](#15.3) <a name='15.3'></a> 使用简写。

  ```javascript
  // bad
  if (name !== '') {
    // ...stuff...
  }

  // good
  if (name) {
    // ...stuff...
  }

  // bad
  if (collection.length > 0) {
    // ...stuff...
  }

  // good
  if (collection.length) {
    // ...stuff...
  }
  ```

- [15.4](#15.4) <a name='15.4'></a> 想了解更多信息，参考 Angus Croll 的 [Truth Equality and JavaScript](http://javascriptweblog.wordpress.com/2011/02/07/truth-equality-and-javascript/#more-2108)。

**[⬆ 返回目录](#table-of-contents)**

<a name="blocks"></a>
## 代码块

- [16.1](#16.1) <a name='16.1'></a> 使用大括号包裹所有的多行代码块。

  ```javascript
  // bad
  if (test)
    return false;

  // good
  if (test) return false;

  // good
  if (test) {
    return false;
  }

  // bad
  function() { return false; }

  // good
  function() {
    return false;
  }
  ```

- [16.2](#16.2) <a name='16.2'></a> 如果通过 `if` 和 `else` 使用多行代码块，把 `else` 放在 `if` 代码块关闭括号的同一行。

  ```javascript
  // bad
  if (test) {
    thing1();
    thing2();
  }
  else {
    thing3();
  }

  // good
  if (test) {
    thing1();
    thing2();
  } else {
    thing3();
  }
  ```


**[⬆ 返回目录](#table-of-contents)**

<a name="comments"></a>
## 注释

- [17.1](#17.1) <a name='17.1'></a> 使用 `/** ... */` 作为多行注释。包含描述、指定所有参数和返回值的类型和值。

  ```javascript
  // bad
  // make() returns a new element
  // based on the passed in tag name
  //
  // @param {String} tag
  // @return {Element} element
  function make(tag) {
    // ...stuff...
    return element;
  }

  // good
  /**
   * make() returns a new element
   * based on the passed in tag name
   *
   * @param {String} tag
   * @return {Element} element
   */
  function make(tag) {
    // ...stuff...
    return element;
  }
  ```

- [17.2](#17.2) <a name='17.2'></a> 使用 `//` 作为单行注释。在评论对象上面另起一行使用单行注释。在注释前插入空行。

  ```javascript
  // bad
  const active = true  // is current tab

  // good
  // is current tab
  const active = true

  // bad
  function getType() {
    console.log('fetching type...');
    // set the default type to 'no type'
    const type = this._type || 'no type'
    return type;
  }

  // good
  function getType() {
    console.log('fetching type...');

    // set the default type to 'no type'
    const type = this._type || 'no type';

    return type;
  }
  ```

- [17.3](#17.3) <a name='17.3'></a> 给注释增加 `FIXME` 或 `TODO` 的前缀可以帮助其他开发者快速了解这是一个需要复查的问题，或是给需要实现的功能提供一个解决方式。这将有别于常见的注释，因为它们是可操作的。使用 `FIXME -- need to figure this out` 或者 `TODO -- need to implement`。

- [17.4](#17.4) <a name='17.4'></a> 使用 `// FIXME`: 标注问题。

  ```javascript
  class Calculator {
    constructor() {
      // FIXME: shouldn't use a global here
      total = 0;
    }
  }
  ```

- [17.5](#17.5) <a name='17.5'></a> 使用 `// TODO`: 标注问题的解决方式。

  ```javascript
  class Calculator {
    constructor() {
      // TODO: total should be configurable by an options param
      this.total = 0;
    }
  }
  ```

**[⬆ 返回目录](#table-of-contents)**

<a name="whitespace"></a>
## 空白

- [18.1](#18.1) <a name='18.1'></a> 使用 2 个空格作为缩进。

  ```javascript
  // bad
  function() {
  ∙∙∙∙const name
  }

  // bad
  function() {
  ∙const name
  }

  // good
  function() {
  ∙∙const name
  }
  ```

- [18.2](#18.2) <a name='18.2'></a> 在花括号前放一个空格。

  ```javascript
  // bad
  function test(){
    console.log('test')
  }

  // good
  function test() {
    console.log('test')
  }

  // bad
  dog.set('attr',{
    age: '1 year',
    breed: 'Bernese Mountain Dog'
  })

  // good
  dog.set('attr', {
    age: '1 year',
    breed: 'Bernese Mountain Dog'
  })
  ```

- [18.3](#18.3) <a name='18.3'></a> 在控制语句（`if`、`while` 等）的小括号前放一个空格。在函数调用及声明中，不在函数的参数列表前加空格。

  ```javascript
  // bad
  if(isJedi) {
    fight ()
  }

  // good
  if (isJedi) {
    fight()
  }

  // bad
  function fight () {
    console.log ('Swooosh!')
  }

  // good
  function fight() {
    console.log('Swooosh!')
  }
  ```

- [18.4](#18.4) <a name='18.4'></a> 使用空格把运算符隔开。

  ```javascript
  // bad
  const x=y+5

  // good
  const x = y + 5
  ```

- [18.5](#18.5) <a name='18.5'></a> 在文件末尾插入一个空行。

  ```javascript
  // bad
  (function(global) {
    // ...stuff...
  })(this)
  ```

  ```javascript
  // bad
  (function(global) {
    // ...stuff...
  })(this)↵
  ↵
  ```

  ```javascript
  // good
  (function(global) {
    // ...stuff...
  })(this)↵
  ```

- [18.5](#18.5) <a name='18.5'></a> 在使用长方法链时进行缩进。使用前面的点 `.` 强调这是方法调用而不是新语句。

  ```javascript
  // bad
  $('#items').find('.selected').highlight().end().find('.open').updateCount()

  // bad
  $('#items').
    find('.selected').
      highlight().
      end().
    find('.open').
      updateCount()

  // good
  $('#items')
    .find('.selected')
      .highlight()
      .end()
    .find('.open')
      .updateCount()

  // bad
  const leds = stage.selectAll('.led').data(data).enter().append('svg:svg').class('led', true)
      .attr('width', (radius + margin) * 2).append('svg:g')
      .attr('transform', 'translate(' + (radius + margin) + ',' + (radius + margin) + ')')
      .call(tron.led);

  // good
  const leds = stage.selectAll('.led')
      .data(data)
    .enter().append('svg:svg')
      .classed('led', true)
      .attr('width', (radius + margin) * 2)
    .append('svg:g')
      .attr('transform', 'translate(' + (radius + margin) + ',' + (radius + margin) + ')')
      .call(tron.led);
  ```

- [18.6](#18.6) <a name='18.6'></a> 在块末和新语句前插入空行。

  ```javascript
  // bad
  if (foo) {
    return bar
  }
  return baz

  // good
  if (foo) {
    return bar
  }

  return baz

  // bad
  const obj = {
    foo() {
    },
    bar() {
    },
  };
  return obj;

  // good
  const obj = {
    foo() {
    },

    bar() {
    },
  };

  return obj;
  ```


**[⬆ 返回目录](#table-of-contents)**

<a name="commas"></a>
## 逗号

- [19.1](#19.1) <a name='19.1'></a> 行首逗号：**不需要**。

  ```javascript
  // bad
  const story = [
      once
    , upon
    , aTime
  ];

  // good
  const story = [
    once,
    upon,
    aTime
  ]

  // bad
  const hero = {
      firstName: 'Ada'
    , lastName: 'Lovelace'
    , birthYear: 1815
    , superPower: 'computers'
  };

  // good
  const hero = {
    firstName: 'Ada',
    lastName: 'Lovelace',
    birthYear: 1815,
    superPower: 'computers'
  };
  ```


**[⬆ 返回目录](#table-of-contents)**

<a name="type-casting--coercion"></a>
## 类型转换

- [21.1](#21.1) <a name='21.1'></a> 在语句开始时执行类型转换。
- [21.2](#21.2) <a name='21.2'></a> 字符串：

  ```javascript
  //  => this.reviewScore = 9;

  // bad
  const totalScore = this.reviewScore + '';

  // good
  const totalScore = String(this.reviewScore);
  ```

- [21.3](#21.3) <a name='21.3'></a> 对数字使用 `parseInt` 转换，并带上类型转换的基数。

  ```javascript
  const inputValue = '4';

  // bad
  const val = new Number(inputValue);

  // bad
  const val = +inputValue;

  // bad
  const val = inputValue >> 0;

  // bad
  const val = parseInt(inputValue);

  // good
  const val = Number(inputValue);

  // good
  const val = parseInt(inputValue, 10);
  ```

- [21.4](#21.4) <a name='21.4'></a> 布尔:

  ```javascript
  const age = 0;

  // bad
  const hasAge = new Boolean(age);

  // good
  const hasAge = Boolean(age);

  // good
  const hasAge = !!age;
  ```


**[⬆ 返回目录](#table-of-contents)**

<a name="naming-conventions"></a>
## 命名规则

- [22.1](#22.1) <a name='22.1'></a> 避免单字母命名。命名应具备描述性。

  ```javascript
  // bad
  function q() {
    // ...stuff...
  }

  // good
  function query() {
    // ..stuff..
  }
  ```

- [22.2](#22.2) <a name='22.2'></a> 使用驼峰式命名对象、函数和实例。

  ```javascript
  // bad
  const OBJEcttsssss = {};
  const this_is_my_object = {};
  function c() {}

  // good
  const thisIsMyObject = {};
  function thisIsMyFunction() {}
  ```

- [22.3](#22.3) <a name='22.3'></a> 使用帕斯卡式命名构造函数或类。

  ```javascript
  // bad
  function user(options) {
    this.name = options.name;
  }

  const bad = new user({
    name: 'nope',
  });

  // good
  class User {
    constructor(options) {
      this.name = options.name;
    }
  }

  const good = new User({
    name: 'yup',
  });
  ```

- [22.4](#22.4) <a name='22.4'></a> 使用下划线 `_` 开头命名私有属性。

  ```javascript
  // bad
  this.__firstName__ = 'Panda';
  this.firstName_ = 'Panda';

  // good
  this._firstName = 'Panda';
  ```

- [22.5](#22.5) <a name='22.5'></a> 别保存 `this` 的引用。使用箭头函数或 Function#bind。

  ```javascript
  // bad
  function foo() {
    const self = this;
    return function() {
      console.log(self);
    };
  }

  // bad
  function foo() {
    const that = this;
    return function() {
      console.log(that);
    };
  }

  // good
  function foo() {
    return () => {
      console.log(this);
    };
  }
  ```

- [22.6](#22.6) <a name='22.6'></a> 如果你的文件只输出一个类，那你的文件名必须和类名完全保持一致。

  ```javascript
  // file contents
  class CheckBox {
    // ...
  }
  export default CheckBox;

  // in some other file
  // bad
  import CheckBox from './checkBox';

  // bad
  import CheckBox from './check_box';

  // good
  import CheckBox from './CheckBox';
  ```

- [22.7](#22.7) <a name='22.7'></a> 当你导出默认的函数时使用驼峰式命名。你的文件名必须和函数名完全保持一致。

  ```javascript
  function makeStyleGuide() {
  }

  export default makeStyleGuide;
  ```

- [22.8](#22.8) <a name='22.8'></a> 当你导出单例、函数库、空对象时使用帕斯卡式命名。

  ```javascript
  const AirbnbStyleGuide = {
    es6: {
    }
  };

  export default AirbnbStyleGuide;
  ```


**[⬆ 返回目录](#table-of-contents)**

<a name="accessors"></a>
## 存取器

- [23.1](#23.1) <a name='23.1'></a> 属性的存取函数不是必须的。
- [23.2](#23.2) <a name='23.2'></a> 如果你需要存取函数时使用 `getVal()` 和 `setVal('hello')`。

  ```javascript
  // bad
  dragon.age();

  // good
  dragon.getAge();

  // bad
  dragon.age(25);

  // good
  dragon.setAge(25);
  ```

- [23.3](#23.3) <a name='23.3'></a> 如果属性是布尔值，使用 `isVal()` 或 `hasVal()`。

  ```javascript
  // bad
  if (!dragon.age()) {
    return false;
  }

  // good
  if (!dragon.hasAge()) {
    return false;
  }
  ```

- [23.4](#23.4) <a name='23.4'></a> 创建 `get()` 和 `set()` 函数是可以的，但要保持一致。

  ```javascript
  class Jedi {
    constructor(options = {}) {
      const lightsaber = options.lightsaber || 'blue';
      this.set('lightsaber', lightsaber);
    }

    set(key, val) {
      this[key] = val;
    }

    get(key) {
      return this[key];
    }
  }
  ```

**[⬆ 返回目录](#table-of-contents)**

<a name="events"></a>
## 事件

- [24.1](#24.1) <a name='24.1'></a> 当给事件附加数据时（无论是 DOM 事件还是私有事件），传入一个哈希而不是原始值。这样可以让后面的贡献者增加更多数据到事件数据而无需找出并更新事件的每一个处理器。例如，不好的写法：

  ```javascript
  // bad
  $(this).trigger('listingUpdated', listing.id);

  ...

  $(this).on('listingUpdated', function(e, listingId) {
    // do something with listingId
  });
  ```

  更好的写法：

  ```javascript
  // good
  $(this).trigger('listingUpdated', { listingId : listing.id });

  ...

  $(this).on('listingUpdated', function(e, data) {
    // do something with data.listingId
  });
  ```

  **[⬆ 返回目录](#table-of-contents)**


## jQuery

- [25.1](#25.1) <a name='25.1'></a> 使用 `$` 作为存储 jQuery 对象的变量名前缀。

  ```javascript
  // bad
  const sidebar = $('.sidebar')

  // good
  const $sidebar = $('.sidebar')
  ```

- [25.2](#25.2) <a name='25.2'></a> 缓存 jQuery 查询。

  ```javascript
  // bad
  function setSidebar() {
    $('.sidebar').hide()
    
    // ...stuff...
    
    $('.sidebar').css({
      'background-color': 'pink'
    });
  }

  // good
  function setSidebar() {
    const $sidebar = $('.sidebar');
    $sidebar.hide();

    // ...stuff...

    $sidebar.css({
      'background-color': 'pink'
    });
  }
  ```

- [25.3](#25.3) <a name='25.3'></a> 对 DOM 查询使用层叠 `$('.sidebar ul')` 或 父元素 > 子元素 `$('.sidebar > ul')`。 [jsPerf](http://jsperf.com/jquery-find-vs-context-sel/16)
- [25.4](#25.4) <a name='25.4'></a> 对有作用域的 jQuery 对象查询使用 `find`。

  ```javascript
  // bad
  $('ul', '.sidebar').hide();

  // bad
  $('.sidebar').find('ul').hide();

  // good
  $('.sidebar ul').hide();

  // good
  $('.sidebar > ul').hide();

  // good
  $sidebar.find('ul').hide();
  ```


# HTML规范




---

## 基本

- 标签要语义化，这与页面可维护性、seo等都有关系 

    参考资料：
    * [Semantic HTML](http://justineo.github.io/slideshows/semantic-html/#/)
    * [语义化的HTML结构到底有什么好处？](http://www.css88.com/archives/1668)
    * [关于语义化 HTML 以及前端架构的一点思考](http://www.oschina.net/translate/about-html-semantics-front-end-architecture)
    

- 嵌套元素必须缩进换行一次（即4个空格），同级元素对齐，且尽量减少DOM层级

```html
<!-- Must Not -->
<div><ul>
<li><strong></strong></li>
<li><strong></strong></li>
</ul>
</div>

<!-- Must -->
<div>
	<ul>
		<li><strong></strong></li>
		<li><strong></strong></li>
	</ul>
</div>
```

- html中，除了统计代码或特殊情况，尽量不出现js代码片段

- 不要在自闭合（self-closing）元素的尾部添加斜线 -- [HTML5 规范](http://dev.w3.org/html5/spec-author-view/syntax.html#syntax-start-tag)中明确说明这是可选的

- 块级元素可以包含内联元素和某些块级元素，内联元素不可以包含块级元素，只能包含内联元素

```html
<!-- Must Not -->
<span>
    <div>wrong</div>
</span>

<!-- Must -->
<div>
    <h2>jikexueyuan</h2>
    <p>IT education</p>
</div>
```

- p标签不可以包含块级元素

- li标签可以包含div以及ul，ul的子元素应该只有li

- 尽量遵循 HTML 标准和语义，但是不要以牺牲实用性为代价。任何时候都要尽量使用最少的标签并保持最小的复杂度。 

- 所有的img标签：
    - 必须添加src属性，懒加载图片也要设置src属性，值为占位符loading图片
    - 不允许出现过时的border属性，使用样式替代
    - 尽可能的加上alt属性，如果alt不知道写什么，暂时可以用网站名代替


## 文档类型
- 全部使用 HTML5 的文档类型申明：`<!DOCTYPE html>`

## 字符编码
- head标签中需要添加编码meta标签
```html
<head>
    <meta charset="UTF-8">
</head>
```
##PC端meta必选项
```html
//IE浏览器 默认使用最新版本渲染
<meta http-equiv = "X-UA-Compatible" content = "IE=edge" >   
//360浏览器默认使用极速模式渲染
<meta name="renderer" content="webkit">     
```
##HTML5标签兼容，能用html5实现的都应该用HTML5
```html
<!--[if lt IE9]> 
<script src="./js/html5.js"></script>
<![endif]-->
```



## 一律使用小写字母
```html
<!-- Must Not -->
<A HREF="/">Home</A>

<!-- Must -->
<a href="/">Home</a>
```

## 属性
- 对于属性的定义，确保全部使用双引号，不使用单引号
```html
<!-- Must Not -->
<img src='Rosegal.png' alt='Rosegal'>
<!-- Must -->
<img src="Rosegal.png" alt="Rosegal">
```

- 以“data-”为前缀来添加自定义属性，避免使用其他命名方式

```html
<!-- Bad -->
<strong orgp="99"></strong>
<!-- Good -->
<strong data-orgp="99"></strong>
```




## 元素并排
块级要和块级并列，内联要和内联并列
```html
<!-- Bad -->
<div>
    <span>我是内联元素</span>
    <p>我是块级元素</p>
</div>

<!-- Good -->
<div>
    <h2></h2>
    <p></p>
</div>
<div>
    <img src="" alt="">
    <a href=""></a>
    <span></span>
</div>
```

## 元素转换
行内元素不可以强制转成块级元素，块级元素不可以强制转成行内元素  

如下做法是不推荐的：  
给div标签设置 inline 属性  
给span标签设置 block 属性

## 资源加载顺序
因为浏览器是自上而下加载网页的，所以html的书写顺序会影响资源的加载顺序，进而影响到用户体验及性能，所以必须要严格控制html书写顺序。
如无特殊结构项目，在可能的条件下，尽量按以下顺序：
- 重要的meta声明标签
- css文件
- 页面主要内容布局标签
- 导航、侧边栏标签
- js文件
- 统计代码


## 属性顺序
HTML 属性应当按照以下给出的顺序依次排列，确保代码的易读性。
- id, name
- class
- data-xxx
- src, for, type, href
- title, alt


## 减少标签的数量
编写 HTML 代码时，尽量避免多余的父元素，减少DOM数量。但永远以“方便拓展”为目标，不能过分减少或过于冗余
```html
<!-- Bad -->
<span class="avatar">
  <img src="...">
</span>

<!-- Good -->
<img class="avatar" src="...">
```

代码验证不是最终目的，真的目的在于让开发者在经过多次的这种验证过程后，能够深刻理解到怎样的语法或写法是非标准和不推荐的，即使在某些场景下被迫要使用非标准写法，也可以做到心中有数。

## 注释
- 模板文件中不允许使用注释格式 <!-- -->，现有的注释全部删除，包括不必要的空格、换行， 保持html的整洁，
 如功能确实复杂需要使用注释，请使用后端语言的注释，这样在浏览器端看不到相关的注释
 
- 确定废弃的功能请在代码中直接删除，而不是注释掉，无法确定可以在svn中单独提交并附上日志以便版本回退， 暂时隐藏的且稍后会放出的功能在模板中请后端语言的注释；



## 参考资料

- [html5 Doctor](http://html5doctor.com/)
- [HTML 5.2](http://w3c.github.io/html/single-page.html#introduction)


