# 前端1

```markup
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset = "UTF-8">
    <title>标题</title>
  </head>
  <body>
    这是我第一个网页
  </body>
</html>

1:<!DOCTYPE html>文档声明，告诉计算机这是一个HTML5文档
2:<html></html> 双标签，所有的文档内容均包含在这个标签里面
3:<head></head>不可见内容，包含文档标题，字符编码等
4:<body></body>可见内容图片，文本表单等所有可见内容
```

### meta标签

`<meta name = "关键字" content = "页面内容" charset = "UTF - 8"></meta>`

> 标签就是描述语义
>
> meta标签定义字符集，关键字，页面描述
>
> 关键字：告诉搜索引擎，这个网站是干嘛的
>
> 页面描述：对页面的描述，简单介绍这个页面是干嘛的

### div标签

`<div>欢迎</div>`

`<br >：换行作用`

### H标签

```markup
<h1>一级标题</h1>
<h2>二级标题</h2>
<h3>三级标题</h3>
<h4>四级标题</h4>
<h5>五级标题</h5>
<h6>六级标题</h6>
```

### P标签

```markup
<p>
段落
</p>
```

### IMG标签

```markup
src 图像的引用地址
alt 表示不管是什么原因，图像无法被显示的时候，出现的替代文字
<img src="" alt="">

height 高度
width 宽度
<img src = "" alt = "" width="" height="">


```

### ​超链接

```markup
<a href="index.html"> 这是一个网页</a>
```

### A标签

```markup
href : 规定链接目标的URL
title ：鼠标悬停在a标签上的时候显示的文本
target：新打开的页面是否在新窗口打开，
        默认是在当前窗口打开，
        当设置target属性值为"_blank"，
        则在新建页面打开。blank是空白的意思。
name：规定锚的名称，一个a标签有name属性，
        就是一个锚点，是用来定位网页的位置。
        [操作：首先在需要点击的位置输入#name(#是代表本页面)，
        然后在需要跳转到的位置的a标签中输入name="name"]
<a href="#tiaozhuan"></a>
​
<a name="tiaozhuan">
```

### 无序列表 ul

```markup
<ul>
  <li>nihao
  </li>
</ul>
```

用来表示一个列表的语义

ul的子标签只能是li，li就是一个容器级的标签，li中可以放任何的东西。

type属性（在ul中设置）：disc\(默认值\)：实心小圆点 ；circle:空心小圆点；square:实心小方块；

### 有序列表 ol \(ordered list\)

```text
<ol>
  <li>nihao
  </li>
</ol>
```

type属性值：1、A、a、I、i、

ol里面只能有li，li是容器级

### div标签

```markup
<div> 是division 是分割的意思，
它是一个容器标签，可以放任何的标签，
通常用于组合块级元素，以便通过CSS来对这些元素进行格式化。
```

### Span 标签

```markup
<span> span是范围的意思，用于对文档中的行内元素进行组合，
这个标签没有固定的样式表现。它提供了一种将文本的一部分，
文档的一部分独立出来的方式
```

### label标签

```markup
<input type="radio" name="sex">河南
<input type="radio" name="sex">北京
input元素有一个id，然后label标签就有一个for属性，和id相同，
就表示绑定了，这个label和input就有绑定关系了
<input type="radio" name="sex" id="henan"><label for="henan"></label>
<input type="radio" name="sex" id="beijing"><label for="beijing"></label>
```

```text
标记通常以下面两种方式中的一种来和表单控件相联系：
将表单控件作为标记标签的内容，这样的就是隐式形式，
或者为 <label> 标签下的 for 属性命名一个目标表单 id，这样就是显式形式。
```

### form 表单

表单是收集用户信息的，让用户填写的、选择的。例如：登陆、注册、基础信息

Form表单里面有action和method属性，action属性就是表示，表单将提交到哪里，method属性就是表示用什么http方法提交。

```markup
<form action="">
    <label for="user">用户名：</label><input type="text"  name="user" id="user" placeholder="请输入你的名字"/><br/><br/>

    <label for="password">密&nbsp;码：</label><input type="password"  name="password1"  id="password" placeholder="请输入你的密码"/>
  </form>


```

