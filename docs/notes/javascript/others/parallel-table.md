---
title: "JavaScript 索引表"
date: "2019-08-24"
---

# JavaScript | 索引对照表

摘录一些常用的方法（且不限于方法，如属性、常量），在全面与精简中尽量作平衡。

表格内每一项时常以内在意义进行排序而非字母顺序排序，请**善用`目录`与 <kbd>Ctrl</kbd>+<kbd>F</kbd>**👍

## 目录 <!-- omit in toc -->

- [数据类型](#数据类型)
  - [Number](#number)
    - [舍入](#舍入)
    - [常量属性](#常量属性)
  - [String](#string)
    - [查找子串](#查找子串)
    - [获取子串](#获取子串)
    - [转义字符](#转义字符)
- [常用库](#常用库)
  - [Math](#math)
    - [舍入](#舍入-1)
    - [其他](#其他)
- [对象](#对象)
  - [Objects](#objects)
  - [Array](#array)
    - [添加/删除元素](#添加删除元素)
    - [查询元素](#查询元素)
    - [数组转换](#数组转换)
    - [迭代元素](#迭代元素)
  - [Map](#map)
  - [Set](#set)
- [HTML DOM](#html-dom)
  - [节点导航](#节点导航)
  - [查找 HTML 元素](#查找-html-元素)
  - [改变 HTML 元素](#改变-html-元素)
  - [增删 HTML 元素](#增删-html-元素)
  - [对象、集合和属性](#对象集合和属性)
  - [事件种类](#事件种类)
  - [nodeType 节点类型](#nodetype-节点类型)
  - [Attribute 特性](#attribute-特性)
- [BOM](#bom)
  - [元素尺寸](#元素尺寸)
  - [页面滚动](#页面滚动)
  - [Timing 事件](#timing-事件)
  - [window.location 对象](#windowlocation-对象)
  - [window.History 对象](#windowhistory-对象)
  - [window.navigator 对象](#windownavigator-对象)

<br/>

注：本文符号对应关系：

| 符号     | 对应                     |
| -------- | ------------------------ |
| *斜体*   | 需要替换为对应内容的标记 |
| [*args*] | 可选参数                 |

<br/>

---

<br/>

## 数据类型

### Number

> 详细解释：[JavaScript Number 对象 | 菜鸟教程](https://www.runoob.com/jsref/jsref-obj-number.html)

#### 舍入

| 方法                         | 描述（返回值）                           |
| ---------------------------- | ---------------------------------------- |
| *num*.toFixed([*len*])       | 指定位小数位数的数字字符串               |
| *num*.toPrecision([*len*])   | 指定长度的数字字符串                     |
| *num*.toExponential([*len*]) | 已被四舍五入并使用指数计数法的数字字符串 |

<br/>

#### 常量属性

| 属性                     | 描述                                       |
| ------------------------ | ------------------------------------------ |
| Number.MAX_VALUE         | 返回 JavaScript 中可能的最大数             |
| Number.MIN_VALUE         | 返回 JavaScript 中可能的最小数             |
| Number.NEGATIVE_INFINITY | 表示负的无穷大（溢出返回）                 |
| Number.NaN               | 表示非数字值（"**N**ot **a** **N**umber"） |
| Number.POSITIVE_INFINITY | 表示无穷大（溢出返回）                     |

<br/>

#### 其他函数 <!-- omit in toc -->

| 方法             | 描述         |
| ---------------- | ------------ |
| *num*.isFinite() | 是否是有限数 |
| *num*.isNaN()    | 是否为 NaN   |

<br/>

### String

> 详细解释：[JavaScript String 对象 | 菜鸟教程](https://www.runoob.com/jsref/jsref-obj-string.html)

#### 查找子串

| 方法                                  | 描述                         |
| ------------------------------------- | ---------------------------- |
| *str*.indexOf(*substr* [, *pos*])     | 顺序查找子串并返回位置       |
| *str*.lastIndexOf(*subStr* [, *pos*]) | 从末尾开始查找子串并返回位置 |
| *str*.includes(*substr* [, *pos*])    | 是否包含子串并返回boolean值  |
| *str*.startsWith(*str2*)              | 是否按某字符串开始           |
| *str*.endsWith(*str2*)                | 是否按某字符串结束           |

<br/>

#### 获取子串

| 方法                                | 描述                         |
| ----------------------------------- | ---------------------------- |
| *str*.slice(*start* [, *end*])      | 支持负值                     |
| *str*.substring(*start* [, *end*])  | 不支持负值，支持start大于end |
| *str*.substr(*start* [, *length*])` | 指定字符串长度而非结束位置   |

推荐使用slice方法。

<br/>

#### 转义字符

| 字符                        | 描述                                    |
| --------------------------- | --------------------------------------- |
| \\n                         | 换行                                    |
| \\r                         | 回车：不单独使用                        |
|                             | Windows文本文件使用 \r\n 组合表示换行符 |
| \\', \\"                    | 引号                                    |
| \\\                         | 反斜线                                  |
| \\t                         | 制表符                                  |
| \\xXX                       | 十六进制的 unicode XX                   |
| \\uXXXX                     | UTF-16 编码的十六进制 unicode 符号      |
| \\u{X…XXXXXX}（1到6个字符） | UTF-32 编码的十六进制 unicode 符号      |

<br/>

### 其他 <!-- omit in toc -->

| 方法                        | 描述                                               |
| --------------------------- | -------------------------------------------------- |
| *str*.charAt(*pos*)         | 获得字符串特定位置字符（也可以使用方括号直接获得） |
| *str*.toLowerCase()         | 转换为小写                                         |
| *str*.toUpperCase()         | 转换为大写                                         |
| *str*.localeCompare(*str2*) | 根据语言比较字符串而非字符代码大小                 |
| *str*.trim()                | 删除字符串前后的空格                               |
| *str*.repeat(*n*)           | 重复字符串 n 次                                    |

<br/>

## 常用库

### Math

#### 舍入

| 方法         | 描述                     |
| ------------ | ------------------------ |
| Math.floor() | 向下舍入                 |
| Math.ceil()  | 向上舍入                 |
| Math.round() | 四舍五入                 |
| Math.trunc() | 只取整数部分（IE不支持） |

这些函数都是取整，如需要保留n位小数，则使用：

- `toFixed(precision)` 方法
- 先乘10<sup>n</sup>，舍完再除10<sup>n</sup>

<br/>

#### 其他

| 方法                   | 描述               |
| ---------------------- | ------------------ |
| Math.random()          | 获得随机数         |
| Math.max(*a, b, c...*) | 返回参数中的最大值 |
| Math.min(*a, b, c...*) | 返回参数中的最小值 |

<br/>

## 对象

### Objects

// TODO

<br/>

### Array

> 详细解释：[JavaScript Array 对象 | 菜鸟教程](https://www.runoob.com/jsref/jsref-obj-array.html)

#### 添加/删除元素

| 方法                                        | 描述                                                               |
| ------------------------------------------- | ------------------------------------------------------------------ |
| push(*...items*)                            | 从结尾添加元素                                                     |
| pop()                                       | 从结尾提取元素                                                     |
| shift()                                     | 从开头提取元素                                                     |
| unshift(*...items*)                         | 从开头添加元素                                                     |
| splice(*pos*, *deleteCount* [, *...items*]) | 从 pos 开始删除 deleteCount 个元素并在当前位置插入元素             |
| slice(*start* [, *end*])                    | 从 start 到 end（不包括end）的元素返回一个新的数组                 |
| concat(*...items*)                          | 返回当前数组所有成员并添加 items（如为数组则提取其中元素）的新数组 |

**注意：** splice 方法会修改数组本身。

<br/>

#### 查询元素

| 方法                          | 描述                                                 |
| ----------------------------- | ---------------------------------------------------- |
| indexOf(*item* [, *pos*])     | 从 pos 开始找到 item 则返回索引，否则返回 -1         |
| lastIndexOf(*item* [, *pos*]) | 从 结尾找到 pos，如找到 item 则返回索引，否则返回 -1 |
| includes(*value*)             | 数组有 value 则返回 true，否则返回 false             |
| find(*func*)                  | 通过函数过滤元素：返回符合 func 条件的第一个值       |
| filter(*func*)                | 通过函数过滤元素：返回符合 func 条件的全部值         |

findIndex 和 find 类似，但返回索引而不是值。

<br/>

#### 数组转换

| 方法           | 描述                                                              |
| -------------- | ----------------------------------------------------------------- |
| map(*func*)    | 从每个元素调用 func 的结果创建一个新数组                          |
| sort(*func*)   | 将数组按func条件判断并排序，然后返回。例：arr.sort((a, b) => a-b) |
| reverse()      | 在原地颠倒数组，然后返回它                                        |
| split(*delim*) | 将字符串按 delim 分隔符拆分为数组并返回                           |
| join(*delim*)  | 将数组按 delim 分隔符黏合为字符串并返回                           |

**注意：** sort 方法、reverse 方法会修改数组本身。

<br/>

#### 迭代元素

| 方法            | 描述                                |
| --------------- | ----------------------------------- |
| forEach(*func*) | 为每个元素调用 func，不返回任何东西 |

<br/>

#### 其他 <!-- omit in toc -->

| 方法                                                | 描述                         |
| --------------------------------------------------- | ---------------------------- |
| Array.isArray(*arr*)                                | 检查 arr 是否是一个数组      |
| Array.from(*object* [, *mapFunction*, *thisValue*]) | 通过给定的对象中创建一个数组 |

<br/>

| 方法                                                          | 描述                                                                              |
| ------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| *arr*.some(*func*)                                            | 对数组每个元素调用函数 func，若**存在**有结果为 true，则返回 true，否则返回 false |
| arr.every(*func*)                                             | 对数组每个元素调用函数 func，若**所有**的结果为 true，则返回 true，否则返回 false |
| *arr*.fill(*value* [, *start*, *end*])                        | 用 value 重复填充数组                                                             |
| reduce(*func(total, currVal [, currIdx, arr])* [, *initVal*]) | 将数组元素计算为一个值（例如数组所有元素累加）                                    |
| *arr*.copyWithin(*target* [, *start*, *end*])                 | 从数组的指定位置拷贝元素到数组的另一个指定位置中（覆盖现有）                      |

<br/>

### Map

| 方法 / 属性               | 描述                                       |
| ------------------------- | ------------------------------------------ |
| new Map()                 | 创建 map                                   |
| *map*.set(*key*, *value*) | 根据键（key）存储值（value）。支持链式调用 |
| *map*.get(*key*)          | 根据键返回值。若该键不存在，返回 undefined |
| *map*.has(*key*)          | 若键存在，返回 true，否则返回 false        |
| *map*.delete(*key*)       | 移除该键的值                               |
| *map*.clear()             | 清空 map                                   |
| *map*.size                | 返回当前元素个数                           |

<br/>

### Set

| 方法 / 属性           | 描述                                                |
| --------------------- | --------------------------------------------------- |
| new Set(*iterable*)   | 创建 set，可以利用可迭代对象（如数组）来创建        |
| *set*.add(*value*)    | 添加值，返回 set 自身                               |
| *set*.delete(*value*) | 删除值，若该 value 存在则返回 true ，否则返回 false |
| *set*.has(*value*)    | 如果 set 中存在该值则返回 true ，否则返回 false     |
| *set*.clear()         | 清空 set                                            |
| *set*.size            | 返回当前元素个数                                    |

<br/>

## HTML DOM

### 节点导航

| 节点属性               | 描述                   |
| ---------------------- | ---------------------- |
| parentNode             | 父节点                 |
| childNodes[nodeNumber] | 第 nodeNumber 位子节点 |
| firstChild             | 首个子节点             |
| lastChild              | 最后一个子节点         |
| nextSibling            | 同一层级的后一个节点   |
| previousSibling        | 同一层级的前一个节点   |

<br/>

### 查找 HTML 元素

| 方法                                            | 描述                          |
| ----------------------------------------------- | ----------------------------- |
| document.getElementById(*id*)                   | 通过 id 来查找 HTML 元素      |
| document.getElementsByTagName(*name*)           | 通过标签名来查找 HTML 元素    |
| document.getElementsByClassName(*name*)         | 通过类名来查找 HTML 元素      |
| document.querySelectorAll(*name-with-selector*) | 通过 CSS 选择器查找 HTML 元素 |

**注意getElement与getElement<u>s</u>的区别**

<br/>

### 改变 HTML 元素

| 方法                                         | 描述                 |
| -------------------------------------------- | -------------------- |
| *element*.innerHTML = *new-html-content*     | 改变元素的 innerHTML |
| *element*.*attribute* = *new-value*          | 改变元素的属性值     |
| *element*.setAttribute(*attribute*, *value*) | 改变元素的属性值     |
| *element*.style.*property* = *new style*     | 改变元素的 CSS 样式  |

<br/>

### 增删 HTML 元素

#### 旧方法 <!-- omit in toc -->

| 方法                                        | 描述             |
| ------------------------------------------- | ---------------- |
| document.createElement(*element*)           | 创建 HTML 元素   |
| *elem*.removeChild(*child*)                 | 删除 HTML 元素   |
| *elem*.appendChild(*child*)                 | 添加 HTML 元素   |
| *elem*.insertBefore(*element*)              | 插入 HTML 元素   |
| *elem*.replaceChild(*newchild*, *oldchild*) | 替换 HTML 元素   |
| document.write(*text*)                      | 写入 HTML 输出流 |

<br/>

#### 新方法 <!-- omit in toc -->

**插入文本或节点**

| 方法                 | 插入位置      |
| -------------------- | ------------- |
| *node*.before()      | node 前面     |
| *node*.prepend()     | node 内部开头 |
| *node*.append()      | node 内部末尾 |
| *node*.after()       | node 后面     |
| *node*.replaceWith() | 替换 node     |

<br/>

**插入 HTML**

*element*.insertAdjacentHTML(*position*, *html*);

| *position* 字符串值 | 插入位置                 |
| ------------------- | ------------------------ |
| beforebegin         | elem 开头位置前插入 html |
| afterbegin          | elem 开头位置后插入 html |
| beforeend           | elem 结束位置前插入 html |
| afterend            | elem 结束位置后插入 html |

<br/>

**其他方法**

| 方法                     | 描述              |
| ------------------------ | ----------------- |
| *node*.remove()          | 移除 *node*       |
| *node*.cloneNode(*bool*) | 克隆节点（深/浅） |

<br/>

### 对象、集合和属性

分为 HTML DOM Level 1 和 HTML DOM Level 3。

| 属性                         | 描述（返回值）                                | DOM |
| ---------------------------- | --------------------------------------------- | --- |
| document.documentElement     | `<html>` 元素                                 | 3   |
| document.head                | `<head>` 元素                                 | 3   |
| document.title               | `<title>` 元素                                | 1   |
| document.body                | `<body>` 元素                                 | 1   |
| document.scripts             | 所有 `<script>` 元素                          | 3   |
| document.images              | 所有 `<img>` 元素                             | 1   |
| document.forms               | 所有 `<form>` 元素                            | 1   |
| document.embeds              | 所有 `<embed>` 元素                           | 3   |
| document.anchors             | 拥有 `name` 属性的所有 `<a>` 元素。           | 1   |
| document.links               | 拥有 `href` 属性的所有 `<area>` 和 `<a>` 元素 | 1   |
| document.cookie              | 文档 cookie                                   | 1   |
| document.doctype             | 文档 doctype                                  | 3   |
| document.documentMode        | 浏览器使用的模式                              | 3   |
| document.readyState          | 文档加载状态                                  | 3   |
| document.inputEncoding       | 文档编码（字符集）                            | 3   |
| document.URL                 | 文档完整 URL                                  | 1   |
| document.documentURI         | 文档 URI                                      | 3   |
| document.baseURI             | 文档绝对基准 URI                              | 3   |
| document.referrer            | 引用的 URI（链接文档）                        | 1   |
| document.domain              | 文档服务器的域名                              | 1   |
| document.lastModified        | 文档更新的日期和时间                          | 3   |
| document.implementation      | DOM 实现                                      | 3   |
| document.strictErrorChecking | 是否强制执行错误检查                          | 3   |

<br/>

不常用：

| 属性               | 描述                                         | DOM |
| ------------------ | -------------------------------------------- | --- |
| document.applets   | 返回所有 `<applet>` 元素（HTML5 不建议使用） | 1   |
| document.domConfig | 废弃。返回 DOM 配置                          | 3   |

<br/>

### 事件种类

| 事件名                   | 描述                                             |
| ------------------------ | ------------------------------------------------ |
| onload / onunload        | 进入/离开 页面时                                 |
| onchange                 | 内容 被改变 时                                   |
| onmouseover / onmouseout | 移入/移出 某个元素的上方时                       |
| onmousedown / onmouseup  | 鼠标按钮 按下/抬起时                             |
| onclick                  | 鼠标按钮点击后（按下与抬起动作都在元素上方完成） |

<br/>

### nodeType 节点类型

| 节点               | 类型 | 例子                                              |
| ------------------ | ---- | ------------------------------------------------- |
| ELEMENT_NODE       | 1    | `<h1>`W3School`</h1>`                             |
| ATTRIBUTE_NODE     | 2    | `class = "heading"` （HTML DOM 弃用，仅 XML DOM） |
| TEXT_NODE          | 3    | `W3School`                                        |
| COMMENT_NODE       | 8    | `<!-- 这是注释 -->`                               |
| DOCUMENT_NODE      | 9    | HTML 文档本身（`<html>` 的父节点）                |
| DOCUMENT_TYPE_NODE | 10   | `<!Doctype html>`                                 |

<br/>

### Attribute 特性

| 方法 / 属性                          | 描述                       |
| ------------------------------------ | -------------------------- |
| *elem*.hasAttribute(*name*)          | 检查是否存在这个特性       |
| *elem*.getAttribute(*name*)          | 获取这个特性               |
| *elem*.setAttribute(*name*, *value*) | 把这个特性设置为 *name* 值 |
| *elem*.removeAttribute(*name*)       | 移除这个特性               |
| *elem*.attributes                    | 所有特性的集合             |

<br/>

## BOM

### 元素尺寸

| 属性        | 包括内容                   | 不包括内容           | 读写性 |
| ----------- | -------------------------- | -------------------- | ------ |
| clientWidth | 元素宽度、内边距           | 边框和外边距         | 只读   |
| offsetWidth | 元素宽度、内边距、边框     | 外边距               | 只读   |
| scrollWidth | 元素宽度、内边距、溢出尺寸 | 边框和外边距         | 可读写 |
| style.width | 元素宽度                   | 内边距、边框和外边距 | 可读写 |

<br/>

### 页面滚动

| 方法                                  | 描述                          |
| ------------------------------------- | ----------------------------- |
| window.pageYOffset/pageXOffset        | 页面当前滚动位置              |
| window.scrollTo(*pageX*, *pageY*)     | 绝对定位                      |
| window.scrollBy(*x*, *y*)             | 相对当前位置滚动              |
| *elem*.scrollIntoView([*topBoolean*]) | *elem* 与 与窗口顶部/底部对齐 |

<br/>

### Timing 事件

| 方法                                    | 描述                                      |
| --------------------------------------- | ----------------------------------------- |
| setTimeout(*function*, *milliseconds*)  | 在等待指定的毫秒数后执行函数。            |
| clearTimeout(*timeoutVariable*)         | 停止执行 `setTimeout()` 中规定的函数。    |
| setInterval(*function*, *milliseconds*) | 持续重复在等待指定的毫秒数后执行该函数。  |
| clearInterval(*timeoutVariable*)        | 停止执行 `clearInterval()` 中规定的函数。 |

其中，*timeoutVariable* 为 `setInterval()` 的返回值。

<br/>

### window.location 对象

| 属性 / 方法            | 描述                       |
| ---------------------- | -------------------------- |
| location.href          | 返回当前页面的 URL         |
| location.hostname      | 返回 web 主机的域名        |
| location.pathname      | 返回当前页面的路径或文件名 |
| location.protocol      | 返回页面的 web 协议        |
| location.assign(*url*) | 加载新文档                 |

<br/>

### window.History 对象

window.history 对象包含浏览器历史，为了保护用户的隐私，JavaScript 访问此对象存在限制。

| 方法              | 描述                         |
| ----------------- | ---------------------------- |
| history.back()    | 等同于在浏览器点击后退按钮   |
| history.forward() | 等同于在浏览器中点击前进按钮 |

<br/>

### window.navigator 对象

window.navigator 对象包含有关访问者的信息。

| 属性 / 方法             | 描述                                     |
| ----------------------- | ---------------------------------------- |
| navigator.appName       | 浏览器应用程序名称                       |
| navigator.appCodeName   | 浏览器应用程序代码名称                   |
| navigator.platform      | 浏览器平台（操作系统）                   |
| navigator.cookieEnabled | cookie 是否启用                          |
| navigator.product       | 浏览器引擎名称                           |
| navigator.appVersion    | 浏览器版本信息                           |
| navigator.userAgent     | 由浏览器发送到服务器的 user-agent header |
| navigator.language      | 浏览器语言                               |
| navigator.onLine        | 浏览器是否在线                           |
| navigator.javaEnabled() | Java 是否已启用                          |
