# 编码规范         

## 一、一般规范         

#### 1. 使用2个空格符缩进         
建议使用2个空格符进行缩进，不要使用tab，因为当在不同的环境或者说是编辑器当中，只有使用2个空格符才能保障在所有环境下具有一致的表现。         

#### 2. 文件命名         
采用（-）横线分隔来命名       

如：         

```
my-script.js
my-camel-case-name.js
my-file.min.css
```
#### 3.组件命名
采用小驼峰命名法，如：

```
home
videosParts
```

#### 4. 变量/函数命名规范         
变量的命名尽量采用匈牙利命名法，驼峰式书写格式，其中，函数和变量以小写字母开头，类（class）则用大写字母开头，尽量少用缩写，即便用也尽量采用常见的一些缩写（如：num = number，btn = button），常量则采用全部字母大写的书写的方式。更多内容可以参见google开源项目风格指南。对于css的书写，尽量赋予选择器以意义，不要出现没有意义的颜色、数字，应把他们与相应的意思对应起来。         
不推荐：         

```
var n; //不明白n的意义
.text-red { color: red; } //红色表示什么意思
```
推荐：         

```
var number;
var num;
function btnChangeColor(color){...}
.text-danger { color: red; }
```

#### 5. 注释         
无论是html、css还是js文件，尽量将注释写清楚。

## 二、HTML规范         

#### 1. 协议引入         
当引入图片或者其他媒体文件时，url所指向的具体路径中不需要指定协议，除非不是http或https协议。         
不推荐：         

```
<script src="http://cdn.com/jquery.min.js"></script>
```
推荐：         

```
<script src="//cdn.com/jquery.min.js"></script>
```
不推荐：         

```
.example {
  background: url("http://example.com/image/bg.jpg");
}
```                  
推荐：         

```
.example {
  background: url("//example.com/image/bg.jpg");
}
```

#### 2. 引入CSS和JavaScript文件         
根据HTML5规范，在引入css和JavaScript文件时一般不需要制定type属性，因为text/css和text/javascript分别是他们的默认值。         

```
<link rel="stylesheet" href="code-guide.css">
<script src="code-guide.js"></script>
```

#### 3. 属性顺序         
HTML属性应当按照以下给出的顺序依次排列，确保代码的易读性。         

```
class, id，name
data-*
src，for，type，href
title，alt
aria-*，role
```
例如：         

```
<a class=".." id=".." data-modal="toggle" href="#">
  example link
</a>
```

#### 4. 减少标签的数量         
编写HTML代码时，尽量避免多余的父元素，很多时候这需要迭代和重构来实现。         
不推荐：         

```
<span class="avatar">
  <img src="...">
</span>
```
推荐：         

```
<img class="avatar" src="...">
```

## 三、CSS规范             
 - 为选择器分组时，将单独的选择器单独放在一行。         
 - 为了代码的易读性，在每个声明块的左花括号前添加一个空格。         
 - 声明块的右花括号应当单独成行。         
 - 每条声明语句的 : 后应该插入一个空格。         
 - 为了获得更准确的错误报告，每条声明都应该独占一行。         
 - 所有声明语句都应当以分号结尾。最后一条声明语句后面的分号是可选的，但是，如果省略这个分号，你的代码可能更易出错。         
 - 对于以逗号分隔的属性值，每个逗号后面都应该插入一个空格（例如，box-shadow）。         
 - 不要在 rgb()、rgba()、hsl()、hsla() 或 rect() 值的内部的逗号后面插入空格。这样利于从多个属性值（既加逗号也加空格）中区分多个颜色值（只加逗号，不加空格）。         
 - 对于属性值或颜色参数，省略小于 1 的小数前面的 0 （例如，.5 代替 0.5；-.5px 代替 -0.5px）。         
 - 十六进制值应该全部小写，例如，#fff。在扫描文档时，小写字符易于分辨，因为他们的形式更易于区分。         
 - 尽量使用简写形式的十六进制值，例如，用 #fff 代替 #ffffff。         
 - 为选择器中的属性添加双引号，例如，input[type="text"]。只有在某些情况下是可选的，但是，为了代码的一致性，建议都加上双引号。         
 - 避免为 0 值指定单位，例如，用 margin: 0; 代替 margin: 0px;。         

```
/* Bad CSS */
.selector, .selector-secondary, .selector[type=text] {
  padding:15px;
  margin:0px 0px 15px;
  background-color:rgba(0, 0, 0, 0.5);
  box-shadow:0px 1px 2px #CCC,inset 0 1px 0 #FFFFFF
}

/* Good CSS */
.selector,
.selector-secondary,
.selector[type="text"] {
  padding: 15px;
  margin-bottom: 15px;
  background-color: rgba(0,0,0,.5);
  box-shadow: 0 1px 2px #ccc, inset 0 1px 0 #fff;
}
```

#### 1. 声明顺序                  
相关属性的声明应该归为一组，能使用简写尽量使用简写，并按照下面的顺序排列：         
1. Position         
2. Box model         
3. Typographic         
4. Visual         
...          
         
```
.declaration-order {
  /* Positioning */
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 100;

  /* Box-model */
  display: block;
  float: right;
  width: 100px;
  height: 100px;

  /* Typography */
  font: normal 13px "Helvetica Neue", sans-serif;
  line-height: 1.5;
  color: #333;
  text-align: center;

  /* Visual */
  background-color: #f5f5f5;
  border: 1px solid #e5e5e5;
  border-radius: 3px;

  /* Misc */
  opacity: 1;
}
```

#### 2. class命名         
 - class 名称中只能出现小写字符和破折号（dashe）（不是下划线，也不是驼峰命名法）。破折号应当用于相关 class 的命名（类似于命名空间）（例如，.btn 和 .btn-danger）。         
 - 避免过度任意的简写。.btn 代表 button，但是 .s 不能表达任何意思。         
 - class 名称应当尽可能短，并且意义明确。         
 - 使用有意义的名称。使用有组织的或目的明确的名称，不要使用表现形式（presentational）的名称。         
 - 基于最近的父 class 或基本（base） class 作为新 class 的前缀。         

```
/* Good example */
.tweet { ... }
.important { ... }
.tweet-header { ... }
```

#### 3. 选择器         
 - 对于通用元素使用 class ，这样利于渲染性能的优化。         
 - 对于经常出现的组件，避免使用属性选择器（例如，[class^="..."]）。浏览器的性能会受到这些因素的影响。         
 - 选择器要尽可能短，并且尽量限制组成选择器的元素个数，建议不要超过 3 ，太多选择器会造成性能查询上的问题。         

```
/* Bad example */
span { ... }
.page-container #stream .stream-item .tweet .tweet-header .username { ... }
.avatar { ... }

/* Good example */
.avatar { ... }
.tweet-header .username { ... }
.tweet .avatar { ... }
```

#### 4. id 还是 class         
 - class应该应用于概念上相似的元素，这些元素可以出现在同一页面上的多个位置，而id应该应用于不同的唯一的元素。 
 - 只有在目标元素非常独特，绝不会对网站上其他地方别的东西使用这个名称时，才会使用id.         
 - 如果你认为以后可能需要相似的元素，就使用class。         

## 四、VueJS相关规范         

#### 1. 综合         
 - 尽量使用ES2016的新特性，尽量使用vue的语法糖省略bind和on。         
 - js里操作数据而不是操作DOM。         
 - 业务逻辑绑定在html中，尽量不在js里绑定。                  
 - 对于html中元素的动态的Attributes，应当使用bind绑定。         
 - 对于html中元素的类，静态的写在class中，动态的使用:class设定。         
 - 如果使用UI插件，尽量在具体的页面中引用某个需要的组件，而不是在全局引用。         

