> 
>
> 
>
> 我的博客
>
> [CSDN](https://blog.csdn.net/qq_42592823?spm=1018.2226.3001.5343)
>
> [掘金](https://juejin.cn/user/721732313820455)

> 我的仓库
>
> [码云](https://gitee.com/zhousujuan)
>
> [github](https://github.com/zhousujuan)

# 前端框架

## Vue

### 条件渲染

#### v-if

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>条件渲染</title>
    <!-- 引入vue -->
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>
<body>
    <div id="root">
        <h2>当前的n的值： {{n}}</h2>
        <button @click="n++">点击我n+1</button>
        <!-- 使用v-if做条件渲染 -->
        <h2 v-if="false">欢迎你！ {{name}}</h2>
        <h2 v-if="n === 1">我出来了，现在是n=1</h2>
    </div>
</body>
<script type="text/javascript">
    Vue.config.productionTip = false;

    new Vue({
        el: '#root',
        data: {
            n: 0,
            name: 'zhousujuan'
        },
    })
</script>
</html>
```



> ```
> v-if
>         写法：
>             (1): v-if="表达式"
>             (2): v-else-if="表达式"
>             (3): v-else="表达式"
>         适用于：切换频率较低的场景
>         特点：不展示的DOM元素直接被移除
>         注意：v-if可以和：v-else-if、v-else一起使用，但是要求结构不能被"打断"。
> ```



#### v-else和v-else-if

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>条件渲染</title>
    <!-- 引入vue -->
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>
<body>
    <div id="root">
        <h2>当前的n的值： {{n}}</h2>
        <button @click="n++">点击我n+1</button>
        <!-- v-else 和 v-else-if -->
        <div v-if="n === 1">当n等于1</div>
        <div v-else-if="n === 2">当n等于2</div>
        <div v-else-if="n === 3">当n等于3</div>
        <div v-else>我是其他</div>
    </div>
</body>
<script type="text/javascript">
    Vue.config.productionTip = false;

    new Vue({
        el: '#root',
        data: {
            n: 0,
            name: 'zhousujuan'
        },
    })
</script>
</html>
```

> 当然这里的v-else-if也可以转换成v-if来展示，但是我们这里的v-if是都要判断，v-else-if是逐层判断，只要有一个是满足条件的，就是跳出，但是v-if是所有的都要判断

#### v-if和tempelate的配合使用

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>条件渲染</title>
    <!-- 引入vue -->
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>
<body>
    <div id="root">
        <h2>当前的n的值： {{n}}</h2>
        <button @click="n++">点击我n+1</button>
        <!-- v-if和tempelate的配合使用 -->
        <template v-if="n===1">
            <h2>hello</h2>
            <h2>你好</h2>
            <h2>深圳</h2>
        </template>
    </div>
</body>
<script type="text/javascript">
    Vue.config.productionTip = false;

    new Vue({
        el: '#root',
        data: {
            n: 0,
            name: 'zhousujuan'
        },
    })
</script>
</html>
```

> template的使用是为了不影响结构，但是只能配合v-if来使用哦

#### v-show

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>条件渲染</title>
    <!-- 引入vue -->
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>
<body>
    <div id="root">
        <h2>当前的n的值： {{n}}</h2>
        <button @click="n++">点击我n+1</button>
        <!-- 使用v-show做条件渲染 -->
        <h2 v-show="false">欢迎你！ {{name}}</h2>
        <h2 v-show="n === 1">我出来了，现在是n=1</h2>
    </div>
</body>
<script type="text/javascript">
    Vue.config.productionTip = false;

    new Vue({
        el: '#root',
        data: {
            n: 0,
            name: 'zhousujuan'
        },
    })
</script>
</html>
```



>     v-show
>         写法：v-show="表达式"
>         适用于：切换频率较高的场景
>         特点: 不展示的DOM元素未被移除，仅仅是使用样式隐藏掉
>

`备注：使用v-if的时候，元素可能无法获取到，而使用v-show一定可以获取到`

------



## React

### 简介

#### 是什么

用于构建用户界面的javascript库

1. 发送请求获取数据
2. 处理数据（过滤或者整理格式等）
3. **操作DOM呈现页面**

前两个部分是自己做，后面一个部分是react帮你操作

> 是一个将数据渲染为html视图的开源javascript库

#### 谁开发的

由facebook开发，并且开源

#### 为什么学

1. 原生JavaScript操作DOM繁琐、效率低（`DOM-API操作UI`）
2. 使用JavaScript直接操作DOM,浏览器会进行大量的**重绘重排**
3. 原生JavaScript没有**组件化**编码方案，代码复用率低。

#### 特点

1. 采用`组件化`模式、`声明式编码`，提高开发效率及组件复用率。
2. 在React Native中可以使用React语法进行`移动端开发`。
   1. 这里学了React Native，只用js也可以开发移动端app
3. 使用`虚拟DOM`+优秀的`Diff算法`，尽量减少与真实DOM的交互

#### 高效的原因

1. 使用虚拟(virtual)DOM,不总是直接操作页面真实DOM
2. DOM Diff算法，最小化页面重绘。

## Angular

------

## AngularJS

> 图标库：[Material Symbols and Icons - Google Fonts](https://fonts.google.com/icons?selected=Material+Icons:sd_storage&icon.query=sort&icon.style=Outlined)
>
> ui库：[AngularJS Material - Demos > Icon](https://material.angularjs.org/latest/demo/icon)
>
> [案例源码](https://gitee.com/zhousujuan/my_note/tree/master/docs/%E5%89%8D%E7%AB%AF/AngularJS)（为了方便，此处的案例源码，我这边直接就启用的是gitee仓库）

### 简介

#### JavaScript 框架。

**AngularJS 是一个 JavaScript 框架。**

它可通过` <script> `标签添加到 HTML 页面。

```js
<script src="http://apps.bdimg.com/libs/angular.js/1.4.6/angular.min.js" rel="external nofollow" rel="external nofollow" rel="external nofollow" ></script>
```

> 建议把脚本放在 <body> 元素的底部。这会提高网页加载速度，因为 HTML 加载不受制于脚本加载。

#### 通过指令扩展了HTML

**AngularJS通过指令扩展了HTML，并且通过表达式绑定数据到 HTML。**

1. AngularJS 通过 **ng-directives** 扩展了 HTML。
2. **ng-app** 指令定义一个 AngularJS 应用程序。
3. **ng-model** 指令把元素值（比如输入域的值）绑定到应用程序。
4. **ng-bind** 指令把应用程序数据绑定到 HTML 视图。

[源码](https://gitee.com/zhousujuan/my_note/blob/master/docs/%E5%89%8D%E7%AB%AF/AngularJS/01.%E7%AE%80%E4%BB%8B/01.AngularJS%E6%89%A9%E5%B1%95%E4%BA%86HTML.html)

```html
<!DOCTYPE html>
<html>
<body>

<div ng-app="">
  <p>在输入框中尝试输入：</p>
  <p>姓名：<input type="text" ng-model="name"></p>
  <p ng-bind="name"></p>
</div>

<script src="http://apps.bdimg.com/libs/angular.js/1.4.6/angular.min.js" rel="external nofollow" rel="external nofollow" rel="external nofollow" ></script>

</body>
</html>
```

[^TODO]: (: 后续的这里将添加一个尝试一下的按钮（或者是点击运行的按钮），实现，用户点击之后，直接在电脑上面通过插件运行代码，查看效果)

> 实例讲解：
>
> 当网页加载完毕，AngularJS 自动开启。
>
> **ng-app** 指令告诉 AngularJS，<div> 元素是 AngularJS **应用程序** 的"所有者"。
>
> **ng-model** 指令把输入域的值绑定到应用程序变量 **name**。
>
> **ng-bind** 指令把应用程序变量 name 绑定到某个段落的 innerHTML。
>
> ===》如果您移除了 **ng-app** 指令，HTML 将直接把表达式显示出来，不会去计算表达式的结果。



#### 是什么？

"AngularJS 是专门为应用程序设计的 HTML。"

AngularJS 使得开发现代的单一页面应用程序（SPAs：Single Page Applications）变得更加容易。

- AngularJS 把应用程序数据绑定到 HTML 元素。
- AngularJS 可以克隆和重复 HTML 元素。
- AngularJS 可以隐藏和显示 HTML 元素。
- AngularJS 可以在 HTML 元素"背后"添加代码。
- AngularJS 支持输入验证。

#### 指令

正如您所看到的，AngularJS 指令是以 **ng** 作为前缀的 HTML 属性。

**ng-init** 指令初始化 AngularJS 应用程序变量。

[源码](https://gitee.com/zhousujuan/my_note/blob/master/docs/%E5%89%8D%E7%AB%AF/AngularJS/01.%E7%AE%80%E4%BB%8B/02.AngularJS%E6%8C%87%E4%BB%A4.html)

```html
<div ng-app="" ng-init="firstName='John'">

	<p>姓名为 <span ng-bind="firstName"></span></p>

</div>
```

> HTML5 允许扩展的（自制的）属性，以 **data-** 开头。
> AngularJS 属性以 **ng-** 开头，但是您可以使用 **data-ng-** 来让网页对 HTML5 有效。

带有有效的 HTML5：

```html
<div data-ng-app="" data-ng-init="firstName='John'">

	<p>姓名为 <span data-ng-bind="firstName"></span></p>

</div>
```



AngularJS已经被用于Google的多款产品当中。

AngularJS是为了克服HTML在构建应用上的不足而设计的。

**AngularJS有着诸多特性，最为核心的是**：`MVC、模块化、自动化双向数据绑定、语义化标签、依赖注入等等`。HTML是一门很好的为静态文本展示设计的声明式语言。

可以构建一个单一页面应用程序（SPAs：Single Page Applications）。

#### **AngularJS的优缺点**

- 优点
  - AngularJS模板功能强大丰富，自带了极其丰富的angular指令。
  - AngularJS是完全可扩展的，与其他库的兼容效果很好，每一个功能可以修改或更换，以满足开发者独特的开发流程和功能的需求。
  - AngularJS是一个比较完善的前端MVC框架，包含服务，模板，数据双向绑定，模块化，路由，过滤器，依赖注入等所有功能；
  - AngularJS是互联网巨人谷歌开发，这也意味着他有一个坚实的基础和社区支持。
- 缺点
  - AngularJS强约束导致学习成本较高，对前端不友好。但遵守 AngularJS 的约定时，生产力会很高，对 Java 程序员友好。
  - AngularJS不利于SEO，因为所有内容都是动态获取并渲染生成的，搜索引擎没法爬取。
  - 性能问题：AngularJS作为 MVVM 框架，因为实现了数据的双向绑定，对于大数组、复杂对象会存在性能问题。

#### 相关网址

- AngularJS官方下载地址：https://angularjs.org/

------

### 表达式

AngularJS 表达式写在双大括号内：`{{ expression }}`。

AngularJS 表达式把数据绑定到 HTML，这与` ng-bind` 指令有异曲同工之妙。

AngularJS 将在表达式书写的位置"输出"数据。

**AngularJS 表达式** 很像 **JavaScript 表达式**：它们可以包含文字、运算符和变量。

实例` {{ 5 + 5 }} `或 `{{ firstName + " " + lastName }}`

[源码](https://gitee.com/zhousujuan/my_note/blob/master/docs/%E5%89%8D%E7%AB%AF/AngularJS/01.%E7%AE%80%E4%BB%8B/03.AngularJS%E8%A1%A8%E8%BE%BE%E5%BC%8F.html)

```html
<!DOCTYPE html>
<html>
<body>

<div ng-app="">
  <p>我的第一个表达式： {{ 5 + 5 }}</p>
</div>

<script src="http://apps.bdimg.com/libs/angular.js/1.4.6/angular.min.js" rel="external nofollow" rel="external nofollow" rel="external nofollow" ></script>

</body>
</html>
```

#### 数字

AngularJS数字就像JavaScript数字

[源码](https://gitee.com/zhousujuan/my_note/blob/master/docs/%E5%89%8D%E7%AB%AF/AngularJS/02.%E8%A1%A8%E8%BE%BE%E5%BC%8F/01.%E6%95%B0%E5%AD%97.html)

```html
<div ng-app="" ng-init="quantity=1;cost=5">

	<p>总价： {{ quantity * cost }}</p>

</div>
```

使用ng-bind的相同实例：

```html
<div ng-app="" ng-init="quantity=1;cost=5">
    <p>总价： <span ng-bind="quantity * cost"></span></p>
</div>
```

> 使用 **ng-init** 不是很常见。



#### 字符串

AngularJS字符串就像JavaScript字符串

[源码](https://gitee.com/zhousujuan/my_note/blob/master/docs/%E5%89%8D%E7%AB%AF/AngularJS/02.%E8%A1%A8%E8%BE%BE%E5%BC%8F/02.%E5%AD%97%E7%AC%A6%E4%B8%B2.html)

```html
<div ng-app="" ng-init="firstName='John'; lastName='Doe'">
    <p> 姓名：{{ firstName + '' + lastName }}</p>
</div>
```

使用ng-bind的相同实例

```html
<div ng-app="" ng-init="firstName='Jhon'; lastName='Doe'">
    <p>姓名： <span ng-bind="fistName + '' + lastName"></span></p>
</div>
```

#### 对象

AngularJS的对象就像JavaScript的对象

[源码](https://gitee.com/zhousujuan/my_note/blob/master/docs/%E5%89%8D%E7%AB%AF/AngularJS/02.%E8%A1%A8%E8%BE%BE%E5%BC%8F/03.%E5%AF%B9%E8%B1%A1.html)

```html
<div ng-app="" ng-init="person={firstName: 'sujuan',lastName: 'zhou'}">
        <p>姓名为：{{person.lastName + person.firstName}}</p>
        <hr>
        <!-- ng-bind -->
        <p>姓名为：<span ng-bind="person.lastName + person.firstName"></span></p>
</div>
```

#### 数组

AngularJS的数组就像JavaScript的数组

[源码](https://gitee.com/zhousujuan/my_note/blob/master/docs/%E5%89%8D%E7%AB%AF/AngularJS/02.%E8%A1%A8%E8%BE%BE%E5%BC%8F/04.%E6%95%B0%E7%BB%84.html)

```html
<div ng-app="" ng-init="points=[1,25,36,22]">
        <p>points的第三个值是： {{points[2]}}</p>

        <hr>

        <p>points的第三个值是： <span ng-bind="points[2]"></span></p>
</div>
```

### 指令

AngularJS 通过被称为 指令 的新属性来扩展 HTML。

AngularJS 指令是扩展的 HTML 属性，带有前缀 `ng-`。

#### ng-app

- `ng-app`指令初始化一个 AngularJS 应用程序。

- 它告诉AngularJS,` <div> `元素是AngularJS应用程序的”所有者“；

- 一个网页可以包含多个运行在不同元素中的AngularJs应用程序
- 定义了 AngularJS 应用程序的 **根元素**。
- 在网页加载完毕时会**自动引导**（自动初始化）应用程序。

#### ng-init

- `ng-init` 指令初始化应用程序数据。
- 为 AngularJS 应用程序定义了 **初始值**。
- 通常情况下，不使用 ng-init。您将使用一个控制器或模块来代替它。

#### ng-model  数据绑定

`ng-model `指令把元素值（比如输入域的值）绑定到应用程序。

**ng-model** 指令也可以：

- 为应用程序数据提供类型验证（number、email、required）。
- 为应用程序数据提供状态（invalid、dirty、touched、error）。
- 为 HTML 元素提供 CSS 类。
- 绑定 HTML 元素到 HTML 表单。

> vue中的v-model和它的用法基本是一致的

[源码](https://gitee.com/zhousujuan/my_note/blob/master/docs/%E5%89%8D%E7%AB%AF/AngularJS/03.%E6%8C%87%E4%BB%A4/1.ng-model.html)

```html
<div ng-app="" ng-init="name = 'zhousujuan'">
        <p>在输入框中输入：</p>
        <p>姓名： <input type="text" ng-model="name"></p>
        <p>效果展示： {{name}}</p>
</div>
```

#### ng-repeat

对于集合中（数组中）的每个项会 **克隆一次 HTML 元素**。

ng-repeat指令会重复一个HTML元素

> 这个相当于vue中的v-for指令

源码

```html
<div ng-app="" ng-init="arr=[111,222,333,444,555,666]">
        <p>使用ng-repeat来循环数组</p>
        <ul>
            <li ng-repeat="list in arr">{{list}}</li>
        </ul>
</div>
```



------



# TypeScript

## 安装

使用国内镜像：

```
npm config set registry https://registry.npmmirror.com
```

安装 typescript：

```
npm install -g typescript
```

安装完成后我们可以使用 **tsc** 命令来执行 TypeScript 的相关代码，以下是查看版本号：

```
$ tsc -v
Version 3.2.2
```

## 基础语法

### 组成

TypeScript 程序由以下几个部分组成：

- 模块
- 函数
- 变量
- 语句和表达式
- 注释

我们可以同时编译多个 ts 文件：

```
tsc file1.ts file2.ts file3.ts
```

### 常用编译参数

tsc 常用编译参数如下所示：

- --help     
  - 显示帮助信息
- --module  
  - 载入扩展模块
- --target  
  - 设置ECMA版本
- --declaration  
  - 额外生成一个 .d.ts扩展名的文件

```
tsc ts-hw.ts --declaration//会生成 ts-hw.d.ts、ts-hw.js 两个文件。
```

- --removeComments  

  - 删除文件的注释

- --out  

  - 编译多个文件并合并到一个输出的文件

- --sourdemap  

  - 生成一个sourcemap（.map）文件

  - sourcemap是一个存储源代码与编译代码对应位置映射的信息文件

- --module nolmplicitAny
  - 在表达式和声明生有隐含的any类型时报错

- --watch
  - 在监视模式下运行编译器。会监视输出文件，在它们改变时重新编译。

### 保留关键字

TypeScript保留关键字如下表所示：

1. break
2. as
3. catch
4. switch
5. case
6. if
7. throw
8. else
9. var
10. number
11. string
12. get
13. module
14. type
15. instanceof
16. typeof
17. public
18. private
19. enum
20. export
21. finally
22. for
23. while
24. void
25. null
26. super
27. this
28. new
29. in
30. return
31. true
32. false
33. any
34. extands
35. static
36. let
37. package
38. implement
39. interface
40. function
41. new
42. try
43. yield
44. const
45. continue
46. do

### 空白和换行

TtypeScript会忽略程序中出现的空格、制表和换行符。

空格、制表通常用来缩进代码、使代码易于阅读和理解

### 区分大小写

### 分号是可选的

每行指令都是一段语句，你可以使用分号或者不使用，分号在TypeScript中是可选的，建议使用

如果写在同一行的多条语句，一定要使用分号来分割，不然就会报错

### 注释

注释和js一样有两种类型

//单行

/**/多行

### TypeScript与面向对象

面向对象是对现实世界理解和抽象的方法

TypeScript是一种面向对象的编程语言

#### 两个概念

面向对象主要有两个概念：对象和类。

- ##### 对象

对象是类的一个实例，有状态和行为。

例如：一条狗是一个对象，它的状态有：颜色、名字、品种；行为有：摇尾巴、叫、吃等。

- 类

类是一个末班，它描述一类对象的行为和状态

- 方法

方法是类的操作的实现步骤

#### 面向对象编程实例

```
class Site  {
    name():void {
        console.log("zhousujuan");
        
    }
}
var obj = new Site();
obj.name();

/*
以上实例定义了一个类Site，该类有一个方法name(),该方法在终端上输出字符串zhousujuan。
new 关键字创建类的对象，该对象调用方法name().
*/
```

编译后生成的 JavaScript 代码如下：

```
var Site = /** @class */ (function () {
    function Site() {
    }
    Site.prototype.name = function () {
        console.log("zhousujuan");
    };
    return Site;
}());
var obj = new Site();
obj.name();
/*
以上实例定义了一个类Site，该类有一个方法name(),该方法在终端上输出字符串zhousujuan。
new 关键字创建类的对象，该对象调用方法name().
*/ 

```

执行以上 JavaScript 代码，输出结果如下:

```
zhousujuan
```

## 基础类型

TypeScript 包含的数据类型如下表:

| 数据类型   | 关键字    | 描述                                                         |
| :--------- | --------- | :----------------------------------------------------------- |
| 任意类型   | any       | 声明为 any 的变量可以赋予任意类型的值。                      |
| 数字类型   | number    | 双精度 64 位浮点值。它可以用来表示整数和分数。                                          `let binaryLiteral: number = 0b1010; // 二进制                  let octalLiteral: number = 0o744;    // 八进制                   let decLiteral: number = 6;    // 十进制                         let hexLiteral: number = 0xf00d;    // 十六进制` |
| 字符串类型 | string    | 一个字符系列，使用单引号（**'**）或双引号（**"**）来表示字符串类型。反引号（**`**）来定义多行文本和内嵌表达式。`let name: string = "Runoob"; let years: number = 5; let words: string = `您好，今年是 ${ name } 发布 ${ years + 1} 周年`;` |
| 布尔类型   | boolean   | 表示逻辑值：true 和 false。`let flag: boolean = true;`       |
| 数组类型   | 无        | 声明变量为数组。`// 在元素类型后面加上[] let arr: number[] = [1, 2]; // 或者使用数组泛型 let arr: Array<number> = [1, 2];` |
| 元组       | 无        | 元组类型用来表示已知元素数量和类型的数组，各元素的类型不必相同，对应位置的类型需要相同。`let x: [string, number]; x = ['Runoob', 1];    // 运行正常 x = [1, 'Runoob'];    // 报错 console.log(x[0]);    // 输出 Runoob` |
| 枚举       | enum      | 枚举类型用于定义数值集合。`enum Color {Red, Green, Blue}; let c: Color = Color.Blue; console.log(c);    // 输出 2` |
| void       | void      | 用于标识方法返回值的类型，表示该方法没有返回值。`function hello(): void {    alert("Hello Runoob"); }` |
| null       | null      | 表示对象值缺失。                                             |
| undefined  | undefined | 用于初始化变量为一个未定义的值                               |
| never      | never     | never 是其它类型（包括 null 和 undefined）的子类型，代表从不会出现的值。 |



**注意：**TypeScript 和 JavaScript 没有整数类型

### Any 类型

任意值是 TypeScript 针对编程时类型不明确的变量使用的一种数据类型，它常用于以下三种情况。

1、变量的值会动态改变时，比如来自用户的输入，任意值类型可以让这些变量跳过编译阶段的类型检查，示例代码如下：

```
let x: any = 1;    // 数字类型
x = 'I am who I am';    // 字符串类型
x = false;    // 布尔类型
```

改写现有代码时，任意值允许在编译时可选择地包含或移除类型检查，示例代码如下：

```
let x: any = 4;
x.ifItExists();    // 正确，ifItExists方法在运行时可能存在，但这里并不会检查
x.toFixed();    // 正确
```

定义存储各种类型数据的数组时，示例代码如下：

```
let arrayList: any[] = [1, false, 'fine'];
arrayList[1] = 100;
```

------

### Null 和 Undefined

#### null

在 JavaScript 中 null 表示 "什么都没有"。

null是一个只有一个值的特殊类型。表示一个空对象引用。

用 typeof 检测 null 返回是 object。

#### undefined

在 JavaScript 中, undefined 是一个没有设置值的变量。

typeof 一个没有值的变量会返回 undefined。

Null 和 Undefined 是其他任何类型（包括 void）的子类型，可以赋值给其它类型，如数字类型，此时，赋值后的类型会变成 null 或 undefined。而在TypeScript中启用严格的空校验（--strictNullChecks）特性，就可以使得null 和 undefined 只能被赋值给 void 或本身对应的类型，示例代码如下：

```
// 启用 --strictNullChecks
let x: number;
x = 1; // 运行正确
x = undefined;    // 运行错误
x = null;    // 运行错误
```

上面的例子中变量 x 只能是数字类型。如果一个类型可能出现 null 或 undefined， 可以用 | 来支持多种类型，示例代码如下：

```
// 启用 --strictNullChecks
let x: number | null | undefined;
x = 1; // 运行正确
x = undefined;    // 运行正确
x = null;    // 运行正确
```

更多内容可以查看：[JavaScript typeof, null, 和 undefined](https://www.runoob.com/js/js-typeof.html)

------

### never 类型

never 是其它类型（包括 null 和 undefined）的子类型，代表从不会出现的值。这意味着声明为 never 类型的变量只能被 never 类型所赋值，在函数中它通常表现为抛出异常或无法执行到终止点（例如无限循环），示例代码如下：

```
let x: never;
let y: number;

// 运行错误，数字类型不能转为 never 类型
x = 123;

// 运行正确，never 类型可以赋值给 never类型
x = (()=>{ throw new Error('exception')})();

// 运行正确，never 类型可以赋值给 数字类型
y = (()=>{ throw new Error('exception')})();

// 返回值为 never 的函数可以是抛出异常的情况
function error(message: string): never {
    throw new Error(message);
}

// 返回值为 never 的函数可以是无法被执行到的终止点的情况
function loop(): never {
    while (true) {}
}
```

## 变量声明

变量是一种使用方便的占位符，用于引用计算机内存地址。

我们可以把变量看做存储数据的容器。

TypeScript 变量的命名规则：

- 变量名称可以包含数字和字母。
- 除了下划线 **_** 和美元 **$** 符号外，不能包含其他特殊字符，包括空格。
- 变量名不能以数字开头。

变量使用前必须先声明，我们可以使用 var 来声明变量。

我们可以使用以下四种方式来声明变量：

声明变量的类型及初始值：

```
var [变量名] : [类型] = 值;
```

例如：

```
var uname:string = "Runoob";
```

声明变量的类型，但没有初始值，变量值会设置为 undefined：

```
var [变量名] : [类型];
```

例如：

```
var uname:string;
```

声明变量并初始值，但不设置类型，该变量可以是任意类型：

```
var [变量名] = 值;
```

例如：

```
var uname = "Runoob";
```

声明变量没有设置类型和初始值，类型可以是任意类型，默认初始值为 undefined：

```
var [变量名];
```

例如：

```
var uname;
```

### 实例

```ts
var uname:string = "Runoob";
var score1:number = 50;
var score2:number = 42.50
var sum = score1 + score2
console.log("名字: "+uname)
console.log("第一个科目成绩: "+score1)
console.log("第二个科目成绩: "+score2)
console.log("总成绩: "+sum)
```

**注意：**变量不要使用 name 否则会与 DOM 中的全局 window 对象下的 name 属性出现了重名。

使用 tsc 命令编译以上代码，得到如下 JavaScript 代码：

```ts
var uname = "Runoob"; 
var score1 = 50; 
var score2 = 42.50; 
var sum = score1 + score2; 
console.log("名字: " + uname); 
console.log("第一个科目成绩: " + score1); 
console.log("第二个科目成绩: " + score2); 
console.log("总成绩: " + sum);
```

执行该 JavaScript 代码输出结果为：

```
名字: Runoob
第一个科目成绩: 50
第二个科目成绩: 42.5
总成绩: 92.5
```

TypeScript 遵循强类型，如果将不同的类型赋值给变量会编译错误，如下实例：

```
var num:number = "hello"     // 这个代码会编译错误
```

------

### 类型断言（Type Assertion）

类型断言可以用来手动指定一个值的类型，即允许变量从一种类型更改为另一种类型。

语法格式：

```
<类型>值
```

或:

```
值 as 类型
```

#### 实例

```ts
var str = '1'  
var str2:number = <number> <any> str   //str、str2 是 string 类型 console.log(str2)
```



### TypeScript 是怎么确定单个断言是否足够

当 S 类型是 T 类型的子集，或者 T 类型是 S 类型的子集时，S 能被成功断言成 T。这是为了在进行类型断言时提供额外的安全性，完全毫无根据的断言是危险的，如果你想这么做，你可以使用 any。

它之所以不被称为**类型转换**，是因为转换通常意味着某种运行时的支持。但是，类型断言纯粹是一个编译时语法，同时，它也是一种为编译器提供关于如何分析代码的方法。

编译后，以上代码会生成如下 JavaScript 代码：

```
var str = '1'; var str2 = str;  //str、str2 是 string 类型 console.log(str2);
```

执行输出结果为：

```
1
```

------

### 类型推断

当类型没有给出时，TypeScript 编译器利用类型推断来推断类型。

如果由于缺乏声明而不能推断出类型，那么它的类型被视作默认的动态 any 类型。

```
var num = 2;    // 类型推断为 number 
console.log("num 变量的值为 "+num);  
num = "12";    // 编译错误 console.log(num);
```



- 第一行代码声明了变量 num 并=设置初始值为 2。 注意变量声明没有指定类型。因此，程序使用类型推断来确定变量的数据类型，第一次赋值为 2，**num** 设置为 number 类型。

- 第三行代码，当我们再次为变量设置字符串类型的值时，这时编译会错误。因为变量已经设置为了 number 类型。

  ```
  error TS2322: Type '"12"' is not assignable to type 'number'.
  ```

------

### 变量作用域

变量作用域指定了变量定义的位置。

程序中变量的可用性由变量作用域决定。

TypeScript 有以下几种作用域：

- **全局作用域** − 全局变量定义在程序结构的外部，它可以在你代码的任何位置使用。
- **类作用域** − 这个变量也可以称为 **字段**。类变量声明在一个类里头，但在类的方法外面。 该变量可以通过类的对象来访问。类变量也可以是静态的，静态的变量可以通过类名直接访问。
- **局部作用域** − 局部变量，局部变量只能在声明它的一个代码块（如：方法）中使用。

以下实例说明了三种作用域的使用：

```
var global_num = 12          // 全局变量 
class Numbers {
num_val = 13;             // 实例变量   
static sval = 10;         // 静态变量      
storeNum():void {       
var local_num = 14;    // 局部变量   
}  
}  
console.log("全局变量为: "+global_num)   
console.log(Numbers.sval)   // 静态变量 
var obj = new Numbers();  
console.log("实例变量: "+obj.num_val)
```

以上代码使用 tsc 命令编译为 JavaScript 代码为：

```
var global_num = 12; // 全局变量 
var Numbers = /** @class */ (function () {    
function Numbers() {        
this.num_val = 13; // 实例变量    }    
Numbers.prototype.storeNum = function () {
var local_num = 14; // 局部变量    
};    
Numbers.sval = 10; // 静态变量    
return Numbers; }()); 
console.log("全局变量为: " + global_num); 
console.log(Numbers.sval); // 静态变量 
var obj = new Numbers(); 
console.log("实例变量: " + obj.num_val);
```

执行以上 JavaScript 代码，输出结果为：

```
全局变量为: 12
10
实例变量: 13
```

如果我们在方法外部调用局部变量 local_num，会报错：

```
error TS2322: Could not find symbol 'local_num'.
```

## 运算符

运算符用于执行程序代码运算，会针对一个以上操作数项目来进行运算。

考虑以下计算：

```
7 + 5 = 12
```

以上实例中 7、5 和 12 是操作数。

运算符 **+** 用于加值。

运算符 **=** 用于赋值。

TypeScript 主要包含以下几种运算：

- 算术运算符
- 逻辑运算符
- 关系运算符
- 按位运算符
- 赋值运算符
- 三元/条件运算符
- 字符串运算符
- 类型运算符

------

### 算术运算符

假定 **y=5**，下面的表格解释了这些算术运算符的操作：

| 运算符 | 描述         | 例子  | x 运算结果 | y 运算结果 |
| :----- | :----------- | :---- | :--------- | :--------- |
| +      | 加法         | x=y+2 | 7          | 5          |
| -      | 减法         | x=y-2 | 3          | 5          |
| *      | 乘法         | x=y*2 | 10         | 5          |
| /      | 除法         | x=y/2 | 2.5        | 5          |
| %      | 取模（余数） | x=y%2 | 1          | 5          |
| ++     | 自增         | x=++y | 6          | 6          |
| x=y++  | 5            | 6     |            |            |
| --     | 自减         | x=--y | 4          | 4          |
| x=y--  | 5            | 4     |            |            |

#### 实例

**var** num1:number = 10
**var** num2:number = 2
**var** res:number = 0

res = num1 + num2
console.log("加:     "+res);

res = num1 - num2;
console.log("减: "+res)

res = num1*num2
console.log("乘:   "+res)

res = num1/num2
console.log("除:  "+res)

res = num1%num2
console.log("余数:  "+res)

num1++
console.log("num1 自增运算: "+num1)

num2--
console.log("num2 自减运算: "+num2)

使用 **tsc** 命令编译以上代码得到如下 JavaScript 代码：

```
var num1 = 10; 
var num2 = 2; 
var res = 0; 
res = num1 + num2; 
console.log("加:        " + res); 
res = num1 - num2; 
console.log("减: " + res); 
res = num1 * num2; 
console.log("乘:    " + res); 
res = num1 / num2; 
console.log("除:   " + res); 
res = num1 % num2; 
console.log("余数:   " + res); 
num1++; 
console.log("num1 自增运算: " + num1); 
num2--; 
console.log("num2 自减运算: " + num2);
```

执行以上 JavaScript 代码，输出结果为：

```
加:        12
减: 8
乘:    20
除:   5
余数:   0
num1 自增运算: 11
num2 自减运算: 1
```

------

### 关系运算符

关系运算符用于计算结果是否为 true 或者 false。

x=5，下面的表格解释了关系运算符的操作：

| 运算符 | 描述       | 比较 | 返回值  |
| :----- | :--------- | :--- | :------ |
| ==     | 等于       | x==8 | *false* |
| x==5   | *true*     |      |         |
| !=     | 不等于     | x!=8 | *true*  |
| >      | 大于       | x>8  | *false* |
| <      | 小于       | x<8  | *true*  |
| >=     | 大于或等于 | x>=8 | *false* |
| <=     | 小于或等于 | x<=8 | *true*  |

### 实例

```
var num1:number = 5; 
var num2:number = 9;  
console.log("num1 的值为: "+num1);  
console.log("num2 的值为:"+num2);  
var res = num1>num2  
console.log("num1 大于n num2: "+res)  
res = num1<num2  
console.log("num1 小于 num2: "+res)    
res = num1>=num2  
console.log("num1 大于或等于  num2: "+res)  
res = num1<=num2 
console.log("num1 小于或等于 num2: "+res)    
res = num1==num2  
console.log("num1 等于 num2: "+res)    
res = num1!=num2   
console.log("num1 不等于 num2: "+res)
```

使用 **tsc** 命令编译以上代码得到如下 JavaScript 代码：

```
var num1 = 5; 
var num2 = 9; 
console.log("num1 的值为: " + num1); 
console.log("num2 的值为:" + num2); 
var res = num1 > num2; 
console.log("num1 大于n num2: " + res); 
res = num1 < num2; 
console.log("num1 小于 num2: " + res); 
res = num1 >= num2; 
console.log("num1 大于或等于  num2: " + res); 
res = num1 <= num2; 
console.log("num1 小于或等于 num2: " + res); 
res = num1 == num2; 
console.log("num1 等于 num2: " + res); 
res = num1 != num2; 
console.log("num1 不等于 num2: " + res);
```

执行以上 JavaScript 代码，输出结果为：

```
num1 的值为: 5
num2 的值为:9
num1 大于n num2: false
num1 小于 num2: true
num1 大于或等于  num2: false
num1 小于或等于 num2: true
num1 等于 num2: false
num1 不等于 num2: true
```

------

------

### 逻辑运算符

逻辑运算符用于测定变量或值之间的逻辑。

给定 x=6 以及 y=3，下表解释了逻辑运算符：

| 运算符 | 描述 | 例子                      |
| :----- | :--- | :------------------------ |
| &&     | and  | (x < 10 && y > 1) 为 true |
| \|\|   | or   | (x==5 \|\| y==5) 为 false |
| !      | not  | !(x==y) 为 true           |

#### 实例

```
var avg:number = 20;  
var percentage:number = 90;   
console.log("avg 值为: "+avg+" ,percentage 值为: "+percentage);     
var res:boolean = ((avg>50)&&(percentage>80));  
console.log("(avg>50)&&(percentage>80): ",res);  
var res:boolean = ((avg>50)||(percentage>80));  
console.log("(avg>50)||(percentage>80): ",res);  
var res:boolean=!((avg>50)&&(percentage>80));  
console.log("!((avg>50)&&(percentage>80)): ",res);
```

使用 **tsc** 命令编译以上代码得到如下 JavaScript 代码：

```
var avg = 20; 
var percentage = 90; 
console.log("avg 值为: " + avg + " ,percentage 值为: " + percentage); 
var res = ((avg > 50) && (percentage > 80)); 
console.log("(avg>50)&&(percentage>80): ", res); 
var res = ((avg > 50) || (percentage > 80)); 
console.log("(avg>50)||(percentage>80): ", res); 
var res = !((avg > 50) && (percentage > 80)); 
console.log("!((avg>50)&&(percentage>80)): ", res);
```

执行以上 JavaScript 代码，输出结果为：

```
avg 值为: 20 ,percentage 值为: 90
(avg>50)&&(percentage>80):  false
(avg>50)||(percentage>80):  true
!((avg>50)&&(percentage>80)):  true
```

### 短路运算符(&& 与 ||)

&& 与 || 运算符可用于组合表达式。 && 运算符只有在左右两个表达式都为 true 时才返回 true。

考虑以下实例：

```
var a = 10 
var result = ( a<10 && a>5)
```

以上实例中 a < 10 与 a > 5 是使用了 && 运算符的组合表达式，第一个表达式返回了 false，由于 && 运算需要两个表达式都为 true，所以如果第一个为 false，就不再执行后面的判断(a > 5 跳过计算)，直接返回 false。

|| 运算符只要其中一个表达式为 true ，则该组合表达式就会返回 true。

考虑以下实例：

```
var a = 10 
var result = ( a>5 || a<10)
```

以上实例中 a > 5 与 a < 10 是使用了 || 运算符的组合表达式，第一个表达式返回了 true，由于 || 组合运算只需要一个表达式为 true，所以如果第一个为 true，就不再执行后面的判断(a < 10 跳过计算)，直接返回 true。

------

### 位运算符

位操作是程序设计中对位模式按位或二进制数的一元和二元操作。



| 运算符 | 描述                                                         | 例子        | 类似于       | 结果 | 十进制 |
| :----- | :----------------------------------------------------------- | :---------- | :----------- | :--- | :----- |
| &      | AND，按位与处理两个长度相同的二进制数，两个相应的二进位都为 1，该位的结果值才为 1，否则为 0。 | x = 5 & 1   | 0101 & 0001  | 0001 | 1      |
| \|     | OR，按位或处理两个长度相同的二进制数，两个相应的二进位中只要有一个为 1，该位的结果值为 1。 | x = 5 \| 1  | 0101 \| 0001 | 0101 | 5      |
| ~      | 取反，取反是一元运算符，对一个二进制数的每一位执行逻辑反操作。使数字 1 成为 0，0 成为 1。 | x = ~ 5     | ~0101        | 1010 | -6     |
| ^      | 异或，按位异或运算，对等长二进制模式按位或二进制数的每一位执行逻辑异按位或操作。操作的结果是如果某位不同则该位为 1，否则该位为 0。 | x = 5 ^ 1   | 0101 ^ 0001  | 0100 | 4      |
| <<     | 左移，把 << 左边的运算数的各二进位全部左移若干位，由 << 右边的数指定移动的位数，高位丢弃，低位补 0。 | x = 5 << 1  | 0101 << 1    | 1010 | 10     |
| >>     | 右移，把 >> 左边的运算数的各二进位全部右移若干位，>> 右边的数指定移动的位数。 | x = 5 >> 1  | 0101 >> 1    | 0010 | 2      |
| >>>    | 无符号右移，与有符号右移位类似，除了左边一律使用0 补位。     | x = 2 >>> 1 | 0010 >>> 1   | 0001 | 1      |

#### 实例

```
var a:number = 2;   // 二进制 10  
var b:number = 3;   // 二进制 11     
var result;          
result = (a & b);      
console.log("(a & b) => ",result)             
result = (a | b);           
console.log("(a | b) => ",result)           
result = (a ^ b);   
console.log("(a ^ b) => ",result);     
result = (~b);  
console.log("(~b) => ",result);  
result = (a << b);  
console.log("(a << b) => ",result);   
result = (a >> b);  
console.log("(a >> b) => ",result);  
result = (a >>> 1);  
console.log("(a >>> 1) => ",result);
```

使用 **tsc** 命令编译以上代码得到如下 JavaScript 代码：

```
var a = 2; // 二进制 10  
var b = 3; // 二进制 11 
var result; 
result = (a & b); 
console.log("(a & b) => ", result); 
result = (a | b); 
console.log("(a | b) => ", result); 
result = (a ^ b); 
console.log("(a ^ b) => ", result); 
result = (~b); 
console.log("(~b) => ", result); 
result = (a << b); 
console.log("(a << b) => ", result); 
result = (a >> b); 
console.log("(a >> b) => ", result); 
result = (a >>> 1); 
console.log("(a >>> 1) => ", result);
```

执行以上 JavaScript 代码，输出结果为：

```
(a & b) =>  2
(a | b) =>  3
(a ^ b) =>  1
(~b) =>  -4
(a << b) =>  16
(a >> b) =>  0
(a >>> 1) =>  1
```

------

### 赋值运算符

赋值运算符用于给变量赋值。

给定 **x=10** 和 **y=5**，下面的表格解释了赋值运算符：

| 运算符                  | 例子   | 实例      | x 值   |
| :---------------------- | :----- | :-------- | :----- |
| = (赋值)                | x = y  | x = y     | x = 5  |
| += (先进行加运算后赋值) | x += y | x = x + y | x = 15 |
| -= (先进行减运算后赋值) | x -= y | x = x - y | x = 5  |
| *= (先进行乘运算后赋值) | x *= y | x = x * y | x = 50 |
| /= (先进行除运算后赋值) | x /= y | x = x / y | x = 2  |



类似的逻辑运算符也可以与赋值运算符联合使用：<<=, >>=, >>=, &=, |= 与 ^=。



#### 实例

```
var a: number = 12  
var b:number = 10    
a = b  
console.log("a = b: "+a)  
a += b console.log("a+=b: "+a)  
a -= b  
console.log("a-=b: "+a)  
a *= b  console.log("a*=b: "+a)  
a /= b  console.log("a/=b: "+a)      
a %= b  console.log("a%=b: "+a)
```

使用 **tsc** 命令编译以上代码得到如下 JavaScript 代码：

```
var a = 12; var b = 10; a = b; 
console.log("a = b: " + a); 
a += b; 
console.log("a+=b: " + a); 
a -= b; 
console.log("a-=b: " + a); 
a *= b; console.log("a*=b: " + a); 
a /= b; console.log("a/=b: " + a); 
a %= b; console.log("a%=b: " + a);
```

执行以上 JavaScript 代码，输出结果为：

```
a = b: 10
a+=b: 20
a-=b: 10
a*=b: 100
a/=b: 10
a%=b: 0
```

------

### 三元运算符 (?)

三元运算有 3 个操作数，并且需要判断布尔表达式的值。该运算符的主要是决定哪个值应该赋值给变量。

```
Test ? expr1 : expr2
```

- Test − 指定的条件语句
- expr1 − 如果条件语句 Test 返回 true 则返回该值
- expr2 − 如果条件语句 Test 返回 false 则返回该值

让我们看下以下实例：

var num:number = -2  var result = num > 0 ? "大于 0" : "小于 0，或等于 0"  console.log(result)

实例中用于判断变量是否大于 0。

使用 tsc 命令编译以上代码得到如下 JavaScript 代码：

var num = -2; var result = num > 0 ? "大于 0" : "小于 0，或等于 0"; console.log(result);

以上实例输出结果如下：

```
小于 0，或等于 0
```

------

### 类型运算符

#### typeof 运算符

typeof 是一元运算符，返回操作数的数据类型。

查看以下实例:

var num = 12  console.log(typeof num);   //输出结果: number

使用 tsc 命令编译以上代码得到如下 JavaScript 代码：

var num = 12; console.log(typeof num); //输出结果: number

以上实例输出结果如下：

```
number
```

#### instanceof

instanceof 运算符用于判断对象是否为指定的类型，后面章节我们会具体介绍它。

------

### 其他运算符

#### 负号运算符(-)

更改操作数的符号，查看以下实例：

var x:number = 4  var y = -x;  console.log("x 值为: ",x);   // 输出结果 4  console.log("y 值为: ",y);   // 输出结果 -4

使用 tsc 命令编译以上代码得到如下 JavaScript 代码：

var x = 4; var y = -x; console.log("x 值为: ", x); // 输出结果 4  console.log("y 值为: ", y); // 输出结果 -4

以上实例输出结果如下：

```
x 值为:  4
y 值为:  -4
```

#### 字符串运算符: 连接运算符 (+)

\+ 运算符可以拼接两个字符串，查看以下实例：

var msg:string = "RUNOOB"+".COM"  console.log(msg)

使用 tsc 命令编译以上代码得到如下 JavaScript 代码：

var msg = "RUNOOB" + ".COM"; console.log(msg);

以上实例输出结果如下：

```
RUNOOB.COM
```



# 数据可视化方案

## Echarts

### 自定义系列（series-custom）

自定义系列可以自定义系列中的图形元素渲染。从而能扩展出不同的图表。

自定义系列可以自定义系列中的图形元素渲染。从而能扩展出不同的图表。

### dataZoom

组件用于区域缩放，从而能自由的关注细节的数据信息，或者概览数据整体，或者去除离群点的影响。

#### 支持的类型

##### 内置型数据区域缩放组件

内置于坐标系中，使用户可以在坐标系上通过鼠标拖拽、鼠标滚轮、手指滑动（触屏上）来缩放或漫游坐标系。

##### 滑动条型数据区域缩放组件

有单独的滑动条，用户在滑动条上进行缩放或漫游

##### 框选型数据区域缩放组件

提供一个选框进行数据区域缩放。即 [toolbox.feature.dataZoom](https://echarts.apache.org/zh/option.html#toolbox.feature.dataZoom)，配置项在 `toolbox` 中。

#### 和数轴的关系

dataZoom主要是对数轴（axis）进行操作（控制数轴的显示范围，或称窗口（window））。

## AntV

### X6

#### 简介

X6 是 AntV 旗下的图编辑引擎，提供了一系列开箱即用的交互组件和简单易用的节点定制能力，方便我们快速搭建 DAG 图、ER 图、流程图等应用。

#### 特性

- 🌱　极易定制：支持使用 SVG/HTML/React/Vue 定制节点样式和交互；
- 🚀　开箱即用：内置 10+ 图编辑配套扩展，如框选、对齐线、小地图等；
- 🧲　数据驱动：基于 MVC 架构，用户更加专注于数据逻辑和业务逻辑；
- 💯　事件驱动：可以监听图表内发生的任何事件。

#### 安装

通过 npm 或 yarn 命令安装 X6。

```shell
# npm
$ npm install @antv/x6 --save

# yarn
$ yarn add @antv/x6
```

安装完成之后，使用 `import` 或 `require` 进行引用。

```ts
import { Graph } from '@antv/x6';
```

如果是直接通过 `script` 标签引入，可以使用下面三个 CDN 中的任何一个，默认返回 X6 的最新版：

- https://unpkg.com/@antv/x6/dist/x6.js
- https://cdn.jsdelivr.net/npm/@antv/x6/dist/x6.js
- https://cdnjs.cloudflare.com/ajax/libs/antv-x6/1.3.20/x6.js (不支持获取最新版)

```html
<script src="https://unpkg.com/@antv/x6/dist/x6.js"></script>
```

对于生产环境，我们推荐使用一个明确的版本号，以避免新版本造成的不可预期的破坏：

- https://unpkg.com/@antv/x6@1.1.1/dist/x6.js
- https://cdn.jsdelivr.net/npm/@antv/x6@1.1.1/dist/x6.js
- https://cdnjs.cloudflare.com/ajax/libs/antv-x6/1.1.1/x6.js

```html
<script src="https://unpkg.com/@antv/x6@1.1.1/dist/x6.js"></script>
```

#### 画布 Graph

在 X6 中，Graph 是图的载体，它包含了图上的所有元素（节点、边等），同时挂载了图的相关操作（如交互监听、元素操作、渲染等）。

##### 平移、缩放、居中

普通画布(未开启 [scroller](https://x6.antv.vision/zh/docs/tutorial/basic/scroller) 模式)通过开启 `panning` 选项来支持拖拽平移。



#### 案例

# Git

Git 是一个开源的分布式版本控制系统，用于敏捷高效地处理任何或小或大的项目。

Git 是 Linus Torvalds 为了帮助管理 Linux 内核开发而开发的一个开放源码的版本控制软件。

Git 与常用的版本控制工具 CVS, Subversion 等不同，它采用了分布式版本库的方式，不必服务器端软件支持。

# Linux



------



# 数据结构

## 简介

数据结构是相互存在一种或多种特定关系的数据元素的集合。

# Docker

##  概述

### docker为什么会出现？

一款产品：开发--上线  两套环境！应用环境，应用配置！

开发

运维

问题：我在我的电脑可以运行！版本更新导致服务不可用！对于运维来说，考验就十分大？

开发即运维!

环境配置四十分麻烦的，每一个机器都要部署环境（集群Redis，ES,  Hadoop ...）!  费时费力。

发布一个项目  （jar +  (Redis  MySQL  jdk  ES)），项目能不能都带上环境安装打包！

之前服务器配置一个应用的环境 Redis MySQL jdk  ES  Hadoop , 配置超麻烦，不能跨平台。

Windows，最后发布到Linux！

传统：开发jar   ，运维来做！

现在：开发打包部署上线，一套流程做完！

docker给以上问题提出了解决方案！

# 打包工具

## Webpack

## Gulp

### 简介

gulp 是基于 node 实现 Web 前端自动化开发的工具，利用它能够极大的提高开发效率。 在 Web 前端开发工作中有很多“重复工作”，比如压缩CSS/JS文件。而这些工作都是有规律的。找到这些规律，并编写 gulp 配置代码,让 gulp 自动执行这些“重复工作”。

#### 说明

Gulp.js是一个自动化构建工具，开发者可以使用它在项目开发过程中自动执行常见任务。

随着互联网的逐步发展，前端前景也越来越好，随之而来的 web 业务也变得复杂化和多元化，所以各种前端构建工具也随之产生，常见的有 Grunt 、 Gulp 、 Webpack 三种。本手册就给大家介绍一下 Gulp。 

Gulp.js 是一个前端构建工具，与 grunt.js 相比，Gulp.js 无需写一大堆繁杂的配置参数，AP I也非常简单，学习起来很容易，而且 Gulp.js 使用的是 node.js 中 stream 来读取和操作数据，其速度更快。如果你还没有使用过前端构建工具，或者觉得 grunt.js 太难用的话，那就尝试一下Gulp.js吧。

#### 优点

1.gulp 将开发流程中让人痛苦或耗时的任务自动化，从而减少你所浪费的时间、创造更大价值。

2.代码优于配置、node 最佳实践、精简的 API 集，gulp 让工作前所未有的简单。

3.基于 node 强大的流(stream)能力，gulp 在构建过程中并不把文件立即写入磁盘，从而提高了构建速度。

4.遵循严格的准则，确保我们的插件结构简单、运行结果可控。
