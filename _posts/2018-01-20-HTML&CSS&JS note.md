---
layout: post
title:  前端基础（HTML & CSS & JS）笔记
date:   2018-01-20 
categories: code
tag: 前端
---

* content
{:toc}






## HTML                               {#HTML}

### 注释：

```html
<!-- 
html在此处写注释 -->
```
### HTML外联样式：

```html
<head>
<link rel="stylesheet" type="text/css" href="cssFilename.css">
</head>
```
### 表格

```html
<!-- 横向表头 -->
<table>
<tr>
  <th>姓名</th>
  <th colspan="2">电话</th> <!-- 横跨两列 --> 
</tr>
<tr>
  <td>Bill Gates</td>
  <td>555 77 854</td>
  <td>555 77 855</td>
</tr>
</table>

<!--纵向表头-->
<table border="1">   <!-- border="0":无边框 -->
<tr>
  <th>姓名</th>
  <td>Bill Gates</td>
</tr>
<tr>
  <th  rowspan="2">电话</th>   <!-- 横跨两行 -->
  <td>555 77 854</td>
</tr>
<tr>
  <td>555 77 855</td>
</tr>
</table>
```
### script

`<script>` 标签用于定义客户端脚本，比如 JavaScript；

`<noscript>` 标签提供无法使用脚本时的替代内容，比方在浏览器禁用脚本时，或浏览器不支持客户端脚本时。


（位于`<head></head>`内）

### head元素：

```html
<head>
	<title>华中科技大学</title>
	<meta charset="utf-8">
	<link rel="stylesheet" type="text/css" href="index.css">
</head>

<!--一些搜索引擎会利用 meta 元素的 name 和 content 属性来索引您的页面。-->
<!--下面的 meta 元素定义页面的描述：-->
<meta name="description" content="Free Web tutorials on HTML, CSS, XML" />

<!--下面的 meta 元素定义页面的关键词：-->
<meta name="keywords" content="HTML, CSS, XML" />

```
### 字符实体

HTML 中的预留字符必须被替换为字符实体。如果希望正确地显示预留字符，我们必须在 HTML 源代码中使用**字符实体**

| 显示结果 | 描述            | 实体名称           | 实体编号    |
| ---- | ------------- | -------------- | ------- |
|      | 空格            | &nbsp;         | &#160;  |
| <    | 小于号           | &lt;           | &#60;   |
| >    | 大于号           | &gt;           | &#62;   |
| &    | 和号            | &amp;          | &#38;   |
| "    | 引号            | &quot;         | &#34;   |
| '    | 撇号            | &apos; (IE不支持) | &#39;   |
| ￠    | 分（cent）       | &cent;         | &#162;  |
| £    | 镑（pound）      | &pound;        | &#163;  |
| ¥    | 元（yen）        | &yen;          | &#165;  |
| €    | 欧元（euro）      | &euro;         | &#8364; |
| §    | 小节            | &sect;         | &#167;  |
| ©    | 版权（copyright） | &copy;         | &#169;  |
| ®    | 注册商标          | &reg;          | &#174;  |
| ™    | 商标            | &trade;        | &#8482; |
| ×    | 乘号            | &times;        | &#215;  |
| ÷    | 除号            | &divide;       | &#247;  |

### 文档类型

<!DOCTYPE> 声明帮助浏览器正确地显示网页。常用声明：

HTML5

```html
<!DOCTYPE html>
```

HTML 4.01

```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"
"http://www.w3.org/TR/html4/loose.dtd">

```

XHTML 1.0

```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```
### 表单`<form></form>`

表单元素：

1. ##### `<input>  `元素

   输入类型type："text"\"password"\"submit"(提交表单数据至表单处理程序的按钮)\"radio"(单选按钮)\"checkbox"(复选框)\"button"(按钮)

   输入限制：

   | 属性           | 描述                                       |
   | ------------ | ---------------------------------------- |
   | disabled     | 规定输入字段应该被禁用。                             |
   | max          | 规定输入字段的最大值。                              |
   | maxlength    | 规定输入字段的最大字符数。                            |
   | min          | 规定输入字段的最小值。                              |
   | pattern      | 规定通过其检查输入值的正则表达式。                        |
   | readonly     | 规定输入字段为只读（无法修改）。                         |
   | required     | 规定输入字段是必需的（必需填写）。                        |
   | size         | 规定输入字段的宽度（以字符计）。                         |
   | step         | 规定输入字段的合法数字间隔。                           |
   | value        | 规定输入字段的默认值。                              |
   | autocomplete | （on/off）规定表单或输入字段是否应该自动完成。当自动完成开启，浏览器会基于用户之前的输入值自动填写值 |
   | autofocus    | 当页面加载时 <input> 元素应该自动获得焦点                |
   | required     | 如果设置，则规定在提交表单之前必须填写输入字段                  |
   | multiple     | 规定允许用户在 <input> 元素中输入一个以上的值。             |

2. ##### `<select>`元素（下拉列表）,`<option>` 元素定义待选择的选项

   ```html
   <select name="cars">
   	<option value="volvo">Volvo</option>	
   	<option value="saab">Saab</option>
   </select
   ```

3. ##### `<textarea>`元素定义多行输入字段（文本域）

   ```html
   <textarea name="message" rows="10" cols="30">
   The cat was playing in the garden.
   </textarea>
   ```

4. ##### `<button>`元素定义可点击的按钮

   ```html
   <button type="button" onclick="alert('Hello World!')">Click Me!</button>
   ```

5. ##### HTML5 `<datalist>`元素

   为` <input>`元素规定预定义选项列表,用户会在他们输入数据时看到预定义选项的下拉列表

   ```html
   <form action="action_page.php">
   <input list="browsers">
   <datalist id="browsers">
      <option value="Internet Explorer">
      <option value="Firefox">
      <option value="Chrome">
      <option value="Opera">
      <option value="Safari">
   </datalist> 
   </form>
   ```

## CSS                          {#CSS}

### 列表横排、无点：

```css
/* 无点 */
ul{
	list-style: none;
}
/* 横排(也可以是其他选择器) */
li{
  	float：left；
}
```
### 横向排版方法：

1. 不断分div，直到div只包含两部分，用float；

2. 用`<ul>`和`<li>` 结合CSS选择器（可多行多列）

3. 改`<div>`的display属性为inline-block；

   display属性常见值：

   | 值            | 描述                         |
   | ------------ | -------------------------- |
   | none         | 此元素不会被显示。                  |
   | block        | 此元素将显示为块级元素，此元素前后会带有换行符。   |
   | inline       | 默认。此元素会被显示为内联元素，元素前后没有换行符。 |
   | inline-block | 行内块元素。（CSS2.1 新增的值）        |

### 多重样式

一般而言，所有的样式会根据下面的规则层叠于一个新的虚拟样式表中，其中数字 4 拥有最高的优先权。

1. 浏览器缺省设置
2. 外部样式表
3. 内部样式表（位于`<head>`标签内部）
4. 内联样式（在 HTML 元素内部）

### 选择器

#### 选择器的分组

```css
h1,h2,h3,h4,h5,h6 {
  color: green;
  }
```

#### 继承

子元素继承父元素选择器中规定的属性，or可以重写

#### 选择器类型

- 类型/元素选择器

  ​

- 类选择器

  ```css
  .important {color:red;}
  p.important {color:red;} /*结合元素选择器*/
  .important.warning {background:silver;}/*同时包含这些类选择器的元素的共同属性*/
  ```

  ```html
  <p class="important warning"> 一个元素同时赋予多个包含多个类选择器
  ```

- ID选择器

  只能使用**一次**；**不能同时使用多个**ID选择器。

  ```css
  #intro {font-weight:bold;}
  ```

- 属性选择器

  ```css
  a[href] {color:red;} /*只对有 href 属性的锚（a 元素）应用样式*/
  *[title] {color:red;} /*把包含标题（title）的所有元素变为红色*/
  a[href="http://www.w3school.com.cn/"][title="W3School"] {color: red;}
  /*根据具体属性值选择*/
  p[class~="important"] {color: red;}/*根据部分属性值选择*/
  ```

- 后代选择器

  ```css
  h1 em {color:red;} /*只对 h1 元素中的所有 em 元素应用样式（无论em 的嵌套层次多深）*/
  ```

- 子元素选择器

  ```css
  h1 > strong {color:red;}/*选择只作为 h1 元素子元素的 strong 元素*/
  ```

- 相邻兄弟选择器

  ```css
  h1 + p {margin-top:50px;}
  /*选择紧接在 h1 元素后出现的段落(h1 和 p 元素拥有共同的父元素)
  用一个结合符只能选择两个相邻兄弟中的第二个元素*/
  ```

- 伪类(pseudo-class)

  | 属性                                       | 描述                    | CSS  |
  | ---------------------------------------- | --------------------- | ---- |
  | [:active](http://www.w3school.com.cn/cssref/pr_pseudo_active.asp) | 向被激活的元素添加样式。          | 1    |
  | [:focus](http://www.w3school.com.cn/cssref/pr_pseudo_focus.asp) | 向拥有键盘输入焦点的元素添加样式。     | 2    |
  | [:hover](http://www.w3school.com.cn/cssref/pr_pseudo_hover.asp) | 当鼠标悬浮在元素上方时，向元素添加样式。  | 1    |
  | [:link](http://www.w3school.com.cn/cssref/pr_pseudo_link.asp) | 向未被访问的链接添加样式。         | 1    |
  | [:visited](http://www.w3school.com.cn/cssref/pr_pseudo_visited.asp) | 向已被访问的链接添加样式。         | 1    |
  | [:first-child](http://www.w3school.com.cn/cssref/pr_pseudo_first-child.asp) | 向元素的第一个子元素添加样式。       | 2    |
  | [:lang](http://www.w3school.com.cn/cssref/pr_pseudo_lang.asp) | 向带有指定 lang 属性的元素添加样式。 | 2    |

  ```css
  selector : pseudo-class {property: value}
  selector.class : pseudo-class {property: value}
  /*与CSS类结合使用*/
  /*锚伪类*/
  a:link {color: #FF0000}		/* 未访问的链接 */
  a:visited {color: #00FF00}	/* 已访问的链接 */
  a:hover {color: #FF00FF}	/* 鼠标移动到链接上 */
  a:active {color: #0000FF}	/* 选定的链接 */
  /*在 CSS 定义中，a:hover 必须被置于 a:link 和 a:visited 之后，才是有效的;
  在 CSS 定义中，a:active 必须被置于 a:hover 之后，才是有效的*/
  ```

- 伪元素(Pseudo-elements)

  | 属性                                       | 描述               | CSS  |
  | ---------------------------------------- | ---------------- | ---- |
  | [:first-letter](http://www.w3school.com.cn/cssref/pr_pseudo_first-letter.asp) | 向文本的第一个字母添加特殊样式。 | 1    |
  | [:first-line](http://www.w3school.com.cn/cssref/pr_pseudo_first-line.asp) | 向文本的首行添加特殊样式。    | 1    |
  | [:before](http://www.w3school.com.cn/cssref/pr_pseudo_before.asp) | 在元素之前添加内容。       | 2    |
  | [:after](http://www.w3school.com.cn/cssref/pr_pseudo_after.asp) | 在元素之后添加内容。       | 2    |

  ```css
  selector:pseudo-element {property:value;}
  selector.class:pseudo-element {property:value;}
  ```

  ​

### 背景background

| 属性                                       | 描述                     |
| ---------------------------------------- | ---------------------- |
| [background](http://www.w3school.com.cn/cssref/pr_background.asp) | 简写属性，作用是将背景属性设置在一个声明中。 |
| [background-attachment](http://www.w3school.com.cn/cssref/pr_background-attachment.asp) | 背景图像是否固定或者随着页面的其余部分滚动。 |
| [background-color](http://www.w3school.com.cn/cssref/pr_background-color.asp) | 设置元素的背景颜色。             |
| [background-image](http://www.w3school.com.cn/cssref/pr_background-image.asp) | 把图像设置为背景。              |
| [background-position](http://www.w3school.com.cn/cssref/pr_background-position.asp) | 设置背景图像的起始位置。           |
| [background-repeat](http://www.w3school.com.cn/cssref/pr_background-repeat.asp) | 设置背景图像是否及如何重复。         |

### 文本属性

| 属性                                       | 描述                                       |
| ---------------------------------------- | ---------------------------------------- |
| [color](http://www.w3school.com.cn/cssref/pr_text_color.asp) | 设置文本颜色                                   |
| [direction](http://www.w3school.com.cn/cssref/pr_text_direction.asp) | 设置文本方向。                                  |
| [line-height](http://www.w3school.com.cn/cssref/pr_dim_line-height.asp) | 设置行高。                                    |
| [letter-spacing](http://www.w3school.com.cn/cssref/pr_text_letter-spacing.asp) | 设置字符间距。                                  |
| [text-align](http://www.w3school.com.cn/cssref/pr_text_text-align.asp) | 对齐元素中的文本。 left/right /center/ justify(两端对齐) |
| [text-decoration](http://www.w3school.com.cn/cssref/pr_text_text-decoration.asp) | 向文本添加修饰。 none(关闭所有装饰)/underline（下划线）/overline（上划线）/line-through（贯穿划线）/blink（闪烁） |
| [text-indent](http://www.w3school.com.cn/cssref/pr_text_text-indent.asp) | 缩进元素中文本的首行。                              |
| text-shadow                              | 设置文本阴影。CSS2 包含该属性，但是 CSS2.1 没有保留该属性。     |
| [text-transform](http://www.w3school.com.cn/cssref/pr_text_text-transform.asp) | 控制元素中的字母。none/uppercase/lowercase/capitalize |
| unicode-bidi                             | 设置文本方向。                                  |
| [white-space](http://www.w3school.com.cn/cssref/pr_text_white-space.asp) | 设置元素中空白的处理方式。                            |
| [word-spacing](http://www.w3school.com.cn/cssref/pr_text_word-spacing.asp) | 设置字间距。                                   |

### 字体属性

| 属性                                       | 描述                                     |
| ---------------------------------------- | -------------------------------------- |
| [font](http://www.w3school.com.cn/cssref/pr_font_font.asp) | 简写属性。作用是把所有针对字体的属性设置在一个声明中。            |
| [font-family](http://www.w3school.com.cn/cssref/pr_font_font-family.asp) | 设置字体系列。                                |
| [font-size](http://www.w3school.com.cn/cssref/pr_font_font-size.asp) | 设置字体的尺寸。                               |
| [font-size-adjust](http://www.w3school.com.cn/cssref/pr_font_font-size-adjust.asp) | 当首选字体不可用时，对替换字体进行智能缩放。（CSS2.1 已删除该属性。） |
| [font-stretch](http://www.w3school.com.cn/cssref/pr_font_font-stretch.asp) | 对字体进行水平拉伸。（CSS2.1 已删除该属性。）             |
| [font-style](http://www.w3school.com.cn/cssref/pr_font_font-style.asp) | 设置字体风格。                                |
| [font-variant](http://www.w3school.com.cn/cssref/pr_font_font-variant.asp) | 以小型大写字体或者正常字体显示文本。                     |
| [font-weight](http://www.w3school.com.cn/cssref/pr_font_weight.asp) | 设置字体的粗细。                               |

### 链接属性

- a:link - 普通的、未被访问的链接
- a:visited - 用户已访问的链接
- a:hover - 鼠标指针位于链接的上方
- a:active - 链接被点击的时刻

### 列表属性

| 属性                                       | 描述                                   |
| ---------------------------------------- | ------------------------------------ |
| [list-style](http://www.w3school.com.cn/cssref/pr_list-style.asp) | 简写属性。用于把所有用于列表的属性设置于一个声明中。（none：无标志） |
| [list-style-image](http://www.w3school.com.cn/cssref/pr_list-style-image.asp) | 将图象设置为列表项标志。                         |
| [list-style-position](http://www.w3school.com.cn/cssref/pr_list-style-position.asp) | 设置列表中列表项标志的位置。                       |
| [list-style-type](http://www.w3school.com.cn/cssref/pr_list-style-type.asp) | 设置列表项标志的类型。                          |

### 表格属性

| 属性                                       | 描述                 |
| ---------------------------------------- | ------------------ |
| [border-collapse](http://www.w3school.com.cn/cssref/pr_tab_border-collapse.asp) | 设置是否把表格边框合并为单一的边框。 |
| [border-spacing](http://www.w3school.com.cn/cssref/pr_tab_border-spacing.asp) | 设置分隔单元格边框的距离。      |
| [caption-side](http://www.w3school.com.cn/cssref/pr_tab_caption-side.asp) | 设置表格标题的位置。         |
| [empty-cells](http://www.w3school.com.cn/cssref/pr_tab_empty-cells.asp) | 设置是否显示表格中的空单元格。    |
| [table-layout](http://www.w3school.com.cn/cssref/pr_tab_table-layout.asp) | 设置显示单元、行和列的算法。     |

### 轮廓

| 属性                                       | 描述               | CSS  |
| ---------------------------------------- | ---------------- | ---- |
| [outline](http://www.w3school.com.cn/cssref/pr_outline.asp) | 在一个声明中设置所有的轮廓属性。 | 2    |
| [outline-color](http://www.w3school.com.cn/cssref/pr_outline-color.asp) | 设置轮廓的颜色。         | 2    |
| [outline-style](http://www.w3school.com.cn/cssref/pr_outline-style.asp) | 设置轮廓的样式。         | 2    |
| [outline-width](http://www.w3school.com.cn/cssref/pr_outline-width.asp) | 设置轮廓的宽度。         | 2    |

### 框模型

![CSS 框模型](http://www.w3school.com.cn/i/ct_boxmodel.gif)

background应用于由**内容和内边距、边框**组成的区域。

#### 样式初始化

```css
* {
  margin: 0;
  padding: 0;
}
```

#### 盒模型百分比

盒模型（margin、padding）的top、bottom、left、right的**百分比值**都是根据**父容器的宽度**来决定的;

#### 盒模型三种简写

（值的顺序：从上外边距 (**top**) 开始围着元素**顺时针旋转**的）

1. ```css
   margin:10px  /*上下左右均为10px*/
   ```

2. ```css
   margin:10px 20px; /*上下:10px;左右：20px*/
   ```

3. ```css
   margin:10px 20px 30px;/*上:10px;左右：20px;下：30px*/
   ```

#### 适应页面居中

```css
margin：auto
```

#### 外边距合并

1. 当一个元素出现在另一个元素上面时，第一个元素的下外边距与第二个元素的上外边距会发生合并
2. 当一个元素包含在另一个元素中时（假设没有内边距或边框把外边距分隔开），它们的上和/或下外边距也会发生合并
3. 一个空元素，它有外边距，但是没有边框或填充。在这种情况下，上外边距与下外边距就碰到了一起，它们会发生合并
4. ​

> 只有**普通文档流**中**块框**的**垂直外边距**才会发生**外边距合并**。行内框、浮动框或绝对定位之间的外边距不会合并

### 定位

#### 定位机制

三种基本的定位机制：**普通流**、**浮动**和**绝对定位**。

- **块级框**从上到下一个接一个地排列，框之间的垂直距离是由框的垂直外边距计算出来。
- **行内框**在一行中水平布置。可以使用**水平内边距、边框和外边距调整它们的间距**。但是，垂直内边距、边框和外边距不影响行内框的高度。由一行形成的水平框称为行框（Line Box），行框的高度总是足以容纳它包含的所有行内框。不过，设置行高可以增加这个框的高度

#### 相对定位

```css
#box_relative {
  position: relative;
  left: 30px;
  top: 20px;
}
```

元素相对于**它的起点**进行移动，保留在文档流中所占空间

![CSS 相对定位实例](http://www.w3school.com.cn/i/ct_css_positioning_relative_example.gif)

#### 绝对定位

```css
#box_relative {
  position: absolute;
  left: 30px;
  top: 20px;
}
```

相对于其**包含块**定位,元素从文档流中**删除**

绝对定位的元素的位置相对于**最近的已定位祖先元素**，如果元素没有已定位的祖先元素，那么它的位置相对于**最初的包含块**

![CSS 绝对定位实例](http://www.w3school.com.cn/i/ct_css_positioning_absolute_example.gif)

绝对定位的框与文档流无关，所以它们可以覆盖页面上的其它元素。可以通过设置 [z-index 属性](http://www.w3school.com.cn/cssref/pr_pos_z-index.asp)来控制这些框的堆放次序。

#### 浮动

- 浮动的框可以向左或向右移动，直到它的外边缘碰到包含框或另一个浮动框的边框为止。

- 由于浮动框不在文档的普通流中，所以文档的普通流中的块框表现得就像浮动框不存在一样。

- 行框和清理：

  - clear属性：clear 属性规定元素的哪一侧不允许其他浮动元素

    ```css
    img{
      float:left;
      clear:both;
    }
    ```

    | 值       | 描述                     |
    | ------- | ---------------------- |
    | left    | 在左侧不允许浮动元素。            |
    | right   | 在右侧不允许浮动元素。            |
    | both    | 在左右两侧均不允许浮动元素。         |
    | none    | 默认值。允许浮动元素出现在两侧。       |
    | inherit | 规定应该从父元素继承 clear 属性的值。 |


### 图片等比缩放

```css
img{						/*元素选择器*/
	width:auto;
 	height:auto;
 	max-width:100%;
	max-height:100%;
}
```

### 设置隐藏/显示元素

```css
h1.hidden {visibility:hidden;}/*隐藏的元素仍需占用与未隐藏之前一样的空间。元素虽然被隐藏了，但仍然会影响布局*/
h1.hidden {display:none;}/*隐藏的元素不会占用任何空间,该元素原本占用的空间也会从页面布局中消失*/
```

visibility属性：

| 值        | 描述                                       |
| -------- | ---------------------------------------- |
| visible  | 默认值。元素是可见的。                              |
| hidden   | 元素是不可见的。                                 |
| collapse | 当在表格元素中使用时，此值可删除一行或一列，但是它不会影响表格的布局。被行或列占据的空间会留给其他内容使用。如果此值被用在其他的元素上，会呈现为 "hidden"。 |
| inherit  | 规定应该从父元素继承 visibility 属性的值。              |

## Java Script                       {#JavaScript}

### 原始JS 

#### 脚本引入：

```html
<!DOCTYPE html>
<html>
	<head>
  	</head>
	<body>
		<script src="myScript.js"></script>
	</body>
</html>
```

在` <head>` 或` <body> `中引用脚本文件都是可以的。实际运行效果与在 `<script> `标签中编写脚本完全一致。

放在`<head>`中与`<body>`中的区别：`<head>`中创建页面时直接加载，`<body>`中可以在元素创建后加载。

> JS:大小写敏感

#### 操作HTML元素

```javascript
function myfunction
{
  document.getElementById("demo").innerHTML="我的第一段 JavaScript";
  
  document.write("<p>我的第一段 JavaScript</p>");
}
/*请使用 document.write() 仅仅向文档输出写内容。如果在文档已完成加载后执行 document.write，整个 HTML 页面将被覆盖*/
```

> js注释：“//”或“/**/”

#### 变量

##### 声明变量：

**var** 关键词来声明变量（不用类型声明），**动态类型**，相同的变量可用作不同的类型

```javascript
var carname; //已声明未赋值:其值实际上是 undefined
var name="Gates", age=56, job="CEO";
```

##### 变量规则：

- 变量必须以字母开头
- 变量也能以 $ 和 _ 符号开头（不过我们不推荐这么做）
- 变量名称对大小写敏感（y 和 Y 是不同的变量）

#### 数据类型

字符串、数字、布尔、数组、对象、Null、Undefined

数字：JavaScript 只有一种数字类型。数字可以带小数点，也可以不带；

数组：

```javascript
var cars=new Array();
cars[0]="Audi";
cars[1]="BMW";
cars[2]="Volvo";
//或
var cars=new Array("Audi","BMW","Volvo");//condensed array
//或
var cars=["Audi","BMW","Volvo"];//literal array
```

对象：对象由花括号分隔。在括号内部，对象的属性以名称和值对的形式 (name : value) 来定义。属性由逗号分隔

```javascript
var person={
	firstname : "Bill",
	lastname : "Gates",
	id : 5566
};
//对象属性有两种寻址方式：
name=person.lastname;
name=person["lastname"];
```

声明变量类型：使用关键词 "new" 来声明其类型，JavaScript 变量均为对象。当声明一个变量时，就创建了一个新的对象

```javascript
var carname=new String;
var x=      new Number;
var y=      new Boolean;
var cars=   new Array;
var person= new Object;
```

Undefined 和 Null
Undefined 这个值表示变量不含有值。
可以通过将变量的值设置为 null 来清空变量。

#### 对象

同一般“面向对象”语法

#### 函数

```javascript
function functionname()
{
	//这里是要执行的代码
}

function myFunction(var1,var2)
{
	//这里是要执行的代码
}

var myFunction = function(){
  //调用函数前一定要声明函数，直接用上边的方法定义函数后直接使用会报错
}
```

#### 运算符

（给定 x=5）

##### 算数运算符

| 运算符  | 描述                           |
| ---- | ---------------------------- |
| +    | 加（可连接字符串，把数字与字符串相加，结果将成为字符串） |
| -    | 减                            |
| *    | 乘                            |
| /    | 除                            |
| %    | 求余数 (保留整数)                   |
| ++   | 累加                           |
| --   | 递减                           |

##### 赋值运算符

| 运算符  | 例子   | 等价于   | 结果   |
| ---- | ---- | ----- | ---- |
| =    | x=y  |       | x=5  |
| +=   | x+=y | x=x+y | x=15 |
| -=   | x-=y | x=x-y | x=5  |
| *=   | x*=y | x=x*y | x=50 |
| /=   | x/=y | x=x/y | x=2  |
| %=   | x%=y | x=x%y | x=0  |

##### 比较运算符

| 运算符  | 描述       | 例子                           |
| ---- | -------- | ---------------------------- |
| ==   | 等于       | x==8 为 false                 |
| ===  | 全等（值和类型） | x===5 为 true；x==="5" 为 false |
| !=   | 不等于      | x!=8 为 true                  |
| >    | 大于       | x>8 为 false                  |
| <    | 小于       | x<8 为 true                   |
| >=   | 大于或等于    | x>=8 为 false                 |
| <=   | 小于或等于    | x<=8 为 true                  |

##### 逻辑运算符

| 运算符  | 描述   |
| ---- | ---- |
| &&   | and  |
| \|\| | or   |
| !    | not  |

##### 条件运算符

```javascript
variablename=(condition)?value1:value2 
```

#### 条件语句

```javascript
if{}
else if{}
else{}

switch(n)
{
case 1:
  执行代码块 1
  break;
case 2:
  执行代码块 2
  break;
default:
  n 与 case 1 和 case 2 不同时执行的代码
}
```

#### 循环语句

```javascript
//for - 循环代码块一定的次数（同C++）
//for/in - 循环遍历对象的属性
for (x in person)
//while - 当指定的条件为 true 时循环指定的代码块
//do/while - 同样当指定的条件为 true 时循环指定的代码块
```

break 语句用于跳出循环。
continue 用于跳过循环中的一个迭代。

#### 错误

- **try** 语句测试代码块的错误。
- **catch** 语句处理错误。
- **throw** 语句创建自定义错误。

```javascript
try
  {
  //在这里运行代码
  }
catch(err)
  {
  //在这里处理错误
  }
throw exception
```

#### HTML DOM （文档对象模型）

![DOM HTML 树](http://www.w3school.com.cn/i/ct_htmltree.gif)

#### 操作html/css

```javascript
//通过 id 查找 HTML 元素
var x=document.getElementById("intro");
//通过标签名查找 HTML 元素
var y=x.getElementsByTagName("p");

//document.write() 可用于直接向 HTML 输出流写内容
document.write(Date());
//改变 HTML 内容
document.getElementById("p1").innerHTML="New text!";
//改变 HTML 属性
document.getElementById("image").src="landscape.jpg";
//改变CSS
document.getElementById(id).style.property=new style
document.getElementById("p2").style.color="blue";

//创建新的 HTML 元素
var para=document.createElement("p");//创建新的 <p> 元素
var node=document.createTextNode("这是新段落。");//创建了一个文本节点,添加文本
para.appendChild(node);//向 <p> 元素追加这个文本节点
var element=document.getElementById("div1");//找到一个已有的元素
element.appendChild(para);//向这个已有的元素追加新元素

//删除已有的 HTML 元素
var parent=document.getElementById("div1");
var child=document.getElementById("p1");
parent.removeChild(child);
```

#### 事件

- 当用户点击鼠标时

  ```javascript
  onclick=function(value)
  ```

- 当网页已加载时

- 当图像已加载时

- 当鼠标移动到元素上时

- 当输入字段被改变时

- 当提交 HTML 表单时

- 当用户触发按键时

事件句柄　(Event Handlers)

| 属性                                       | 此事件发生在何时...        |
| ---------------------------------------- | ------------------ |
| [onabort](http://www.w3school.com.cn/jsref/event_onabort.asp) | 图像的加载被中断。          |
| [onblur](http://www.w3school.com.cn/jsref/event_onblur.asp) | 元素失去焦点。            |
| [onchange](http://www.w3school.com.cn/jsref/event_onchange.asp) | 域的内容被改变。           |
| [onclick](http://www.w3school.com.cn/jsref/event_onclick.asp) | 当用户点击某个对象时调用的事件句柄。 |
| [ondblclick](http://www.w3school.com.cn/jsref/event_ondblclick.asp) | 当用户双击某个对象时调用的事件句柄。 |
| [onerror](http://www.w3school.com.cn/jsref/event_onerror.asp) | 在加载文档或图像时发生错误。     |
| [onfocus](http://www.w3school.com.cn/jsref/event_onfocus.asp) | 元素获得焦点。            |
| [onkeydown](http://www.w3school.com.cn/jsref/event_onkeydown.asp) | 某个键盘按键被按下。         |
| [onkeypress](http://www.w3school.com.cn/jsref/event_onkeypress.asp) | 某个键盘按键被按下并松开。      |
| [onkeyup](http://www.w3school.com.cn/jsref/event_onkeyup.asp) | 某个键盘按键被松开。         |
| [onload](http://www.w3school.com.cn/jsref/event_onload.asp) | 一张页面或一幅图像完成加载。     |
| [onmousedown](http://www.w3school.com.cn/jsref/event_onmousedown.asp) | 鼠标按钮被按下。           |
| [onmousemove](http://www.w3school.com.cn/jsref/event_onmousemove.asp) | 鼠标被移动。             |
| [onmouseout](http://www.w3school.com.cn/jsref/event_onmouseout.asp) | 鼠标从某元素移开。          |
| [onmouseover](http://www.w3school.com.cn/jsref/event_onmouseover.asp) | 鼠标移到某元素之上。         |
| [onmouseup](http://www.w3school.com.cn/jsref/event_onmouseup.asp) | 鼠标按键被松开。           |
| [onreset](http://www.w3school.com.cn/jsref/event_onreset.asp) | 重置按钮被点击。           |
| [onresize](http://www.w3school.com.cn/jsref/event_onresize.asp) | 窗口或框架被重新调整大小。      |
| [onselect](http://www.w3school.com.cn/jsref/event_onselect.asp) | 文本被选中。             |
| [onsubmit](http://www.w3school.com.cn/jsref/event_onsubmit.asp) | 确认按钮被点击。           |
| [onunload](http://www.w3school.com.cn/jsref/event_onunload.asp) | 用户退出页面。            |

标准 Event 属性

| 属性                                       | 描述                      |
| ---------------------------------------- | ----------------------- |
| [bubbles](http://www.w3school.com.cn/jsref/event_bubbles.asp) | 返回布尔值，指示事件是否是起泡事件类型。    |
| [cancelable](http://www.w3school.com.cn/jsref/event_cancelable.asp) | 返回布尔值，指示事件是否可拥可取消的默认动作。 |
| [currentTarget](http://www.w3school.com.cn/jsref/event_currenttarget.asp) | 返回其事件监听器触发该事件的元素。       |
| [eventPhase](http://www.w3school.com.cn/jsref/event_eventphase.asp) | 返回事件传播的当前阶段。            |
| [target](http://www.w3school.com.cn/jsref/event_target.asp) | 返回触发此事件的元素（事件的目标节点）。    |
| [timeStamp](http://www.w3school.com.cn/jsref/event_timestamp.asp) | 返回事件生成的日期和时间。           |
| [type](http://www.w3school.com.cn/jsref/event_type.asp) | 返回当前 Event 对象表示的事件的名称。  |

标准 Event 方法

下面列出了 2 级 DOM 事件标准定义的方法。IE 的事件模型不支持这些方法：

| 方法                                       | 描述                   |
| ---------------------------------------- | -------------------- |
| [initEvent()](http://www.w3school.com.cn/jsref/event_initevent.asp) | 初始化新创建的 Event 对象的属性。 |
| [preventDefault()](http://www.w3school.com.cn/jsref/event_preventdefault.asp) | 通知浏览器不要执行与事件关联的默认动作。 |
| [stopPropagation()](http://www.w3school.com.cn/jsref/event_stoppropagation.asp) | 不再派发事件。              |

#### 正则表达式（RegExp）

js中：RegExp 对象用于存储检索模式

```javascript
var patt1=new RegExp("e");
```

RegExp 对象的方法：

- test()：检索字符串中的指定值。返回值是 true 或 false

- exec() ：检索字符串中的指定值。返回值是被找到的值。如果没有发现匹配，则返回 null

  ```javascript
  //检索"e"
  var patt1=new RegExp("e");
  document.write(patt1.exec("The best things in life are free")); 
  //上述返回值：e

  /*g参数（global）：
  找到第一个 "e"，并存储其位置;如果再次运行 exec()，则从存储的位置开始检索，并找到下一个 "e"，并存储其位置*/
  var patt1=new RegExp("e","g");
  do
  {
  	result=patt1.exec("The best 	things in life are free");
  	document.write(result);
  }
  while (result!=null)
  //结果:eeeeeenull
  ```

  ​

- compile() ：用于改变 RegExp。
  compile() 既可以改变检索模式，也可以添加或删除第二个参数。

#### JS Window

**浏览器对象模型 (BOM)** 使 JavaScript 有能力与浏览器“对话”

所有浏览器都支持 *window* 对象。它表示浏览器窗口

window.screen 对象包含有关用户屏幕的信息。

window.location 对象用于获得当前页面的地址 (URL)，并把浏览器重定向到新的页面。

window.history 对象包含浏览器的历史。

window.navigator 对象包含有关访问者浏览器的信息。

##### Window 对象属性

| 属性                                       | 描述                                       |
| ---------------------------------------- | ---------------------------------------- |
| [closed](http://www.w3school.com.cn/jsref/prop_win_closed.asp) | 返回窗口是否已被关闭。                              |
| [defaultStatus](http://www.w3school.com.cn/jsref/prop_win_defaultstatus.asp) | 设置或返回窗口状态栏中的默认文本。                        |
| [document](http://www.w3school.com.cn/jsref/dom_obj_document.asp) | 对 Document 对象的只读引用。请参阅 [Document 对象](http://www.w3school.com.cn/jsref/dom_obj_document.asp)。 |
| [history](http://www.w3school.com.cn/jsref/dom_obj_history.asp) | 对 History 对象的只读引用。请参数 [History 对象](http://www.w3school.com.cn/jsref/dom_obj_history.asp)。 |
| [innerheight](http://www.w3school.com.cn/jsref/prop_win_innerheight_innerwidth.asp) | 返回窗口的文档显示区的高度。                           |
| [innerwidth](http://www.w3school.com.cn/jsref/prop_win_innerheight_innerwidth.asp) | 返回窗口的文档显示区的宽度。                           |
| length                                   | 设置或返回窗口中的框架数量。                           |
| [location](http://www.w3school.com.cn/jsref/dom_obj_location.asp) | 用于窗口或框架的 Location 对象。请参阅 [Location 对象](http://www.w3school.com.cn/jsref/dom_obj_location.asp)。 |
| [name](http://www.w3school.com.cn/jsref/prop_win_name.asp) | 设置或返回窗口的名称。                              |
| [Navigator](http://www.w3school.com.cn/jsref/dom_obj_navigator.asp) | 对 Navigator 对象的只读引用。请参数 [Navigator 对象](http://www.w3school.com.cn/jsref/dom_obj_navigator.asp)。 |
| [opener](http://www.w3school.com.cn/jsref/prop_win_opener.asp) | 返回对创建此窗口的窗口的引用。                          |
| [outerheight](http://www.w3school.com.cn/jsref/prop_win_outerheight.asp) | 返回窗口的外部高度。                               |
| [outerwidth](http://www.w3school.com.cn/jsref/prop_win_outerwidth.asp) | 返回窗口的外部宽度。                               |
| pageXOffset                              | 设置或返回当前页面相对于窗口显示区左上角的 X 位置。              |
| pageYOffset                              | 设置或返回当前页面相对于窗口显示区左上角的 Y 位置。              |
| parent                                   | 返回父窗口。                                   |
| [Screen](http://www.w3school.com.cn/jsref/dom_obj_screen.asp) | 对 Screen 对象的只读引用。请参数 [Screen 对象](http://www.w3school.com.cn/jsref/dom_obj_screen.asp)。 |
| [self](http://www.w3school.com.cn/jsref/prop_win_self.asp) | 返回对当前窗口的引用。等价于 Window 属性。                |
| [status](http://www.w3school.com.cn/jsref/prop_win_status.asp) | 设置窗口状态栏的文本。                              |
| [top](http://www.w3school.com.cn/jsref/prop_win_top.asp) | 返回最顶层的先辈窗口。                              |
| window                                   | window 属性等价于 self 属性，它包含了对窗口自身的引用。       |
| screenLeftscreenTopscreenXscreenY        | 只读整数。声明了窗口的左上角在屏幕上的的 x 坐标和 y 坐标。IE、Safari 和 Opera 支持 screenLeft 和 screenTop，而 Firefox 和 Safari 支持 screenX 和 screenY。 |

##### Window 对象方法

| 方法                                       | 描述                              |
| ---------------------------------------- | ------------------------------- |
| [alert()](http://www.w3school.com.cn/jsref/met_win_alert.asp) | 显示带有一段消息和一个确认按钮的警告框。            |
| [blur()](http://www.w3school.com.cn/jsref/met_win_blur.asp) | 把键盘焦点从顶层窗口移开。                   |
| [clearInterval()](http://www.w3school.com.cn/jsref/met_win_clearinterval.asp) | 取消由 setInterval() 设置的 timeout。  |
| [clearTimeout()](http://www.w3school.com.cn/jsref/met_win_cleartimeout.asp) | 取消由 setTimeout() 方法设置的 timeout。 |
| [close()](http://www.w3school.com.cn/jsref/met_win_close.asp) | 关闭浏览器窗口。                        |
| [confirm()](http://www.w3school.com.cn/jsref/met_win_confirm.asp) | 显示带有一段消息以及确认按钮和取消按钮的对话框。        |
| [createPopup()](http://www.w3school.com.cn/jsref/met_win_createpopup.asp) | 创建一个 pop-up 窗口。                 |
| [focus()](http://www.w3school.com.cn/jsref/met_win_focus.asp) | 把键盘焦点给予一个窗口。                    |
| [moveBy()](http://www.w3school.com.cn/jsref/met_win_moveby.asp) | 可相对窗口的当前坐标把它移动指定的像素。            |
| [moveTo()](http://www.w3school.com.cn/jsref/met_win_moveto.asp) | 把窗口的左上角移动到一个指定的坐标。              |
| [open()](http://www.w3school.com.cn/jsref/met_win_open.asp) | 打开一个新的浏览器窗口或查找一个已命名的窗口。         |
| [print()](http://www.w3school.com.cn/jsref/met_win_print.asp) | 打印当前窗口的内容。                      |
| [prompt()](http://www.w3school.com.cn/jsref/met_win_prompt.asp) | 显示可提示用户输入的对话框。                  |
| [resizeBy()](http://www.w3school.com.cn/jsref/met_win_resizeby.asp) | 按照指定的像素调整窗口的大小。                 |
| [resizeTo()](http://www.w3school.com.cn/jsref/met_win_resizeto.asp) | 把窗口的大小调整到指定的宽度和高度。              |
| [scrollBy()](http://www.w3school.com.cn/jsref/met_win_scrollby.asp) | 按照指定的像素值来滚动内容。                  |
| [scrollTo()](http://www.w3school.com.cn/jsref/met_win_scrollto.asp) | 把内容滚动到指定的坐标。                    |
| [setInterval()](http://www.w3school.com.cn/jsref/met_win_setinterval.asp) | 按照指定的周期（以毫秒计）来调用函数或计算表达式。       |
| [setTimeout()](http://www.w3school.com.cn/jsref/met_win_settimeout.asp) | 在指定的毫秒数后调用函数或计算表达式。             |

##### JavaScript 计时

计时单位:ms(毫秒)

关键方法：

1. setTimeout()：未来的某时执行代码

   ```javascript
   var t=setTimeout("javascript语句",毫秒)
   
   t=setTimeout("timedCount()",1000)//无穷循环
   ```

2. clearTimeout()：取消setTimeout()

   ```javascript
   clearTimeout(setTimeout_variable)
   
    clearTimeout(t)
   ```

3. setInterval() : 按照指定的周期（以毫秒计）来调用函数或计算表达式。
   setInterval() 方法会不停地调用函数，直到 clearInterval() 被调用或窗口被关闭。由 setInterval() 返回的 ID 值可用作 clearInterval() 方法的参数。

   ```javascript
   var t = setInterval(code,millisec[,"lang"])
   //code:必需。要调用的函数或要执行的代码串。
   //millisec:必需。周期性执行或调用 code 之间的时间间隔，以毫秒计。
   //t:返回值，一个可以传递给 Window.clearInterval() 从而取消对 code 的周期性执行的值。
   ```

4. clearInterval() :可取消由 setInterval() 设置的 timeout。参数必须是由 setInterval() 返回的 ID 值。

   ```javascript
   clearInterval(id_of_setinterval)
   //id_of_setinterval:由 setInterval() 返回的 ID 值。
   ```

##### JavaScript Cookies

cookie 用来识别用户。cookie 是存储于访问者的计算机中的变量。每当同一台计算机通过浏览器请求某个页面时，就会发送这个 cookie。你可以使用 JavaScript 来创建和取回 cookie 的值

有关cookie的例子：

- 名字 cookie

  当访问者首次访问页面时，他或她也许会填写他/她们的名字。名字会存储于 cookie 中。当访问者再次访问网站时，他们会收到类似 "Welcome John Doe!" 的欢迎词。而名字则是从 cookie 中取回的。

- 密码 cookie

  当访问者首次访问页面时，他或她也许会填写他/她们的密码。密码也可被存储于 cookie 中。当他们再次访问网站时，密码就会从 cookie 中取回。

- 日期 cookie

  当访问者首次访问你的网站时，当前的日期可存储于 cookie 中。当他们再次访问网站时，他们会收到类似这样的一条消息："Your last visit was on Tuesday August 11, 2005!"。日期也是从 cookie 中取回的。

创建与储存：

```javascript
function setCookie(c_name,value,expiredays)
{
	var exdate=new Date()
	exdate.setDate(exdate.getDate()+expiredays)
	document.cookie=c_name+ "=" +escape(value)+
((expiredays==null) ? "" : ";expires="+exdate.toGMTString())
}
/*上面这个函数中的参数存有 cookie 的名称、值以及过期天数。在上面的函数中，首先将天数转换为有效的日期，然后将 cookie 名称、值及其过期日期存入 document.cookie 对象。*/

function getCookie(c_name)
{
	if (document.cookie.length>0)
  	{
  		c_start=document.cookie.indexOf(c_name + "=")
  		if (c_start!=-1)
    	{ 
    		c_start=c_start + c_name.length+1 
    		c_end=document.cookie.indexOf(";",c_start)
    		if (c_end==-1) c_end=document.cookie.length
          	{
          		return unescape(document.cookie.substring(c_start,c_end))
          	}
    			
    	} 
  	}
	return ""
}
/*创建另一个函数来检查是否已设置 cookie。首先会检查 document.cookie 对象中是否存有 cookie。假如 document.cookie 对象存有某些 cookie，那么会继续检查我们指定的 cookie 是否已储存。如果找到了我们要的 cookie，就返回值，否则返回空字符串。*/

function checkCookie()
{
	username=getCookie('username')
	if (username!=null && username!="")
  	{	alert('Welcome again '+username+'!')	}
	else 
  	{
  		username=prompt('Please enter your name:',"")
  		if (username!=null && username!="")
    	{
    		setCookie('username',username,365)
    	}
  	}
}
/*如果 cookie 已设置，则显示欢迎词，否则显示提示框来要求用户输入名字*/
```

### jQuery

#### 引入

```html
<!DOCTYPE html>
	<html>
	<head>
		<script type="text/javascript" src="jquery.js"></script>   <! 本地-->
      <script src="http://ajax.googleapis.com/ajax/libs/jquery/1.8.0/jquery.min.js">
</script>	<! Google CDN-->
      <script src="http://ajax.aspnetcdn.com/ajax/jQuery/jquery-1.8.0.js">
</script>	<! Microsoft CDN-->
	</head>
	<body>
	</body>
</html>
```

#### 基础语法

**$(selector).action()**

- 美元符号定义 jQuery
- 选择符（selector）“查询”和“查找” HTML 元素
- jQuery 的 action() 执行对元素的操作

| 语法                   | 描述                                       |
| -------------------- | ---------------------------------------- |
| $(this)              | 当前 HTML 元素                               |
| $("p")               | 所有 <p> 元素                                |
| $("p.intro")         | 所有 class="intro" 的 <p> 元素                |
| $(".intro")          | 所有 class="intro" 的元素                     |
| $("#intro")          | id="intro" 的元素                           |
| $("ul li:first")     | 每个 <ul> 的第一个 <li> 元素                     |
| $("[href$='.jpg']")  | 所有带有以 ".jpg" 结尾的属性值的 href 属性             |
| $("div#intro .head") | id="intro" 的 <div> 元素中的所有 class="head" 的元素 |

与**".getElementById"**区别:

jquery选择器 $(#id) 返回的是**jquery对象**，用document.getElementById( id )返回的是**DOM对象**。

jquery对象可以使用两种方式**转换为DOM对象**: [ index ] 和 .get( index )

- **$(#id)[0]**     得到DOM对象
- **$(#id).get( 0 )**   得到DOM对象

文档就绪函数：

所有 jQuery 函数位于一个 document ready 函数中：

```javascript
$(document).ready(function(){
--- jQuery functions go here ----
});
```

#### jQuery 事件

| Event 函数                                 | 绑定函数至                                    |
| ---------------------------------------- | ---------------------------------------- |
| $(document).ready(function)              | 将函数绑定到文档的就绪事件（当文档完成加载时）                  |
| $(selector).click(function)              | 触发或将函数绑定到被选元素的**点击**（按下+松开）事件            |
| $(selector).dblclick(function)           | 触发或将函数绑定到被选元素的双击事件                       |
| $(selector).focus(function)              | 触发或将函数绑定到被选元素的获得焦点事件                     |
| $(selector).mouseover(function)          | 被选元素的**鼠标悬停**事件。                         |
| $(selector).mouseout(function)           | 被选元素的**鼠标指针移开**事件                        |
| $(selector).mouseenter(function)         | 被选元素**鼠标指针进入（穿过）**事件。                    |
| $(selector).mouseleave(function)         | 被选元素的**鼠标指针离开**事件                        |
| $(selector).mousedown(function)          | 被选元素的**鼠标按下**事件                          |
| $(selector).mouseup(function)            | 被选元素的**鼠标松开**事件                          |
| $(selector).hover(inFunction,outFunction) | 被选元素的**鼠标悬停**事件。inFunction:必需，规定 mouseover 事件发生时运行的函数；outFunction：可选，规定 mouseout 事件发生时运行的函数。 如果只规定了一个函数，则它将会在 mouseover 和 mouseout 事件上运行。 |

不论鼠标指针穿过**被选元素或其子元素**，都会触发 **mouseover/mouseout** 事件。

只有在鼠标指针穿过被选元素时，才会触发 **mouseenter/mouseleave** 事件。

#### jQuery 效果

##### 基本效果

- 隐藏 hide()
- 显示 show()
- 显示/隐藏切换 toggle()
- 淡入 fadeIn()
- 淡出 fadeOut()
- 淡入淡出切换 fadeToggle()
- 渐变为给定的不透明度（值介于 0 与 1 之间）fadeTo()
- 向下滑动 slideDown()
- 向上滑动 slideUp() 
- 下滑上滑切换 slideToggle()
- 在完成之前停止动画或效果 stop()

```javascript
//均为可选参数
$(selector).hide(speed,callback);
$(selector).show(speed,callback);
$(selector).toggle(speed,callback);
$(selector).fadeIn(speed,callback);
$(selector).fadeOut(speed,callback);
$(selector).fadeToggle(speed,callback);
$(selector).fadeTo(speed,opacity,callback);

$(selector).stop(stopAll,goToEnd);
/*可选的 stopAll 参数规定是否应该清除动画队列。默认是 false，即仅停止活动的动画，允许任何排入队列的动画向后执行。
可选的 goToEnd 参数规定是否立即完成当前动画。默认是 false。
因此，默认地，stop() 会清除在被选元素上指定的当前动画。*/
```

##### 动画

```javascript
$(selector).animate({params},speed,callback);
/*必需的params: 定义形成动画的 CSS 属性。
可选的speed:参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒。
可选的callback:参数是动画完成后所执行的函数名称。*/

//操作多个属性
$("div").animate({
    left:'250px',
    opacity:'0.5',
    height:'150px',
    width:'150px'
});

//使用相对值
$("button").click(function(){
  $("div").animate({
    left:'250px',
    height:'+=150px',
    width:'+=150px'
  });
});

//使用预定义的值,可以把属性的动画值设置为 "show"、"hide" 或 "toggle"
$("button").click(function(){
  $("div").animate({
    height:'toggle'
  });
});

//队列功能,在彼此之后编写多个 animate() 调用，jQuery 会创建包含这些方法调用的“内部”队列。然后逐一运行这些 animate 调用
$("button").click(function(){
  var div=$("div");
  div.animate({height:'300px',opacity:'0.4'},"slow");
  div.animate({width:'300px',opacity:'0.8'},"slow");
  div.animate({height:'100px',opacity:'0.4'},"slow");
  div.animate({width:'100px',opacity:'0.8'},"slow");
});
```

> 当使用 animate() 时，必须**使用 Camel 标记法**书写所有的属性名，比如，必须使用 **paddingLeft** 而不是 padding-left，使用 **marginRight** 而不是 margin-right，等等

##### 停止动画

```javascript
$(selector).stop(stopAll,goToEnd);
//用于停止动画或效果
/*可选的 stopAll 参数规定是否应该清除动画队列。默认是 false，即仅停止活动的动画，允许任何排入队列的动画向后执行。
可选的 goToEnd 参数规定是否立即完成当前动画。默认是 false。
因此，默认地，stop() 会清除在被选元素上指定的当前动画*/
```

### AJAX

AJAX = Asynchronous JavaScript and XML（异步的 JavaScript 和 XML）。

AJAX 不是新的编程语言，而是一种使用现有标准的新方法。

AJAX 是与服务器交换数据并更新部分网页的艺术，在不重新加载整个页面的情况下。

#### XMLHttpRequest(XHR)

##### 创建 XMLHttpRequest 对象

XMLHttpRequest 是 AJAX 的基础, 所有现代浏览器均支持 XMLHttpRequest 对象（IE5 和 IE6 使用 ActiveXObject）。XMLHttpRequest 用于在后台与服务器交换数据。这意味着可以在不重新加载整个网页的情况下，对网页的某部分进行更新。

```javascript
var xmlhttp = new XMLHttpRequest();
```

应对IE5\IE6兼容性：

```javascript
var xmlhttp;
if (window.XMLHttpRequest)
  {// code for IE7+, Firefox, Chrome, Opera, Safari
  xmlhttp=new XMLHttpRequest();
  }
else
  {// code for IE6, IE5
  xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
  }
```

##### 向服务器发送请求

```javascript
xmlhttp.open("GET","test1.txt",true);
xmlhttp.send();
```

| 方法                           | 描述                                       |
| ---------------------------- | ---------------------------------------- |
| open(*method*,*url*,*async*) | 规定请求的类型、URL 以及是否异步处理请求。**method**：请求的类型，GET 或 POST；**url**：文件在服务器上的位置；**async**：true（异步）或 false（同步） |
| send(*string*)               | 将请求发送到服务器。**string**：仅用于 POST 请求         |

**GET 还是 POST**

与 POST 相比，GET 更简单也更快，并且在大部分情况下都能用。

然而，在以下情况中，请使用 POST 请求：

- 无法使用缓存文件（更新服务器上的文件或数据库）
- 向服务器发送大量数据（POST 没有数据量限制）
- 发送包含未知字符的用户输入时，POST 比 GET 更稳定也更可靠

```javascript
xmlhttp.open("GET","demo_get.asp",true);
xmlhttp.send();
```

**异步 - True 或 False**

AJAX 指的是异步 JavaScript 和 XML（Asynchronous JavaScript and XML）。

XMLHttpRequest 对象如果要用于 AJAX 的话，其 open() 方法的 async 参数必须设置为 true。

对于 web 开发人员来说，发送异步请求是一个巨大的进步。很多在服务器执行的任务都相当费时。AJAX 出现之前，这可能会引起应用程序挂起或停止。

通过 AJAX，JavaScript 无需等待服务器的响应，而是：

- 在等待服务器响应时执行其他脚本
- 当响应就绪后对响应进行处理

```javascript
当使用 async=true 时，请规定在响应处于 onreadystatechange 事件中的就绪状态时执行的函数：
xmlhttp.onreadystatechange=function()
  {
  if (xmlhttp.readyState==4 && xmlhttp.status==200)
    {
  document.getElementById("myDiv").innerHTML=xmlhttp.responseText;
    }
  }
xmlhttp.open("GET","test1.txt",true);
xmlhttp.send();
```

##### 服务器响应

如需获得来自服务器的响应，请使用 XMLHttpRequest 对象的 responseText 或 responseXML 属性。

| 属性           | 描述              |
| ------------ | --------------- |
| responseText | 获得字符串形式的响应数据。   |
| responseXML  | 获得 XML 形式的响应数据。 |

**responseText 属性**

如果来自服务器的响应并非 XML，请使用 responseText 属性。

responseText 属性返回字符串形式的响应，因此您可以这样使用：

```javascript
document.getElementById("myDiv").innerHTML=xmlhttp.responseText;
```

**responseXML 属性**

如果来自服务器的响应是 XML，而且需要作为 XML 对象进行解析，请使用 responseXML 属性：

请求 [books.xml](http://www.w3school.com.cn/example/xmle/books.xml) 文件，并解析响应：

```javascript
xmlhttp.onreadystatechange=function()
  {
  if (xmlhttp.readyState==4 && xmlhttp.status==200)
    {
    xmlDoc=xmlhttp.responseXML;
    txt="";
    x=xmlDoc.getElementsByTagName("title");
    for (i=0;i<x.length;i++)
      {
      txt=txt + x[i].childNodes[0].nodeValue + "<br />";
      }
    document.getElementById("myDiv").innerHTML=txt;
    }
  }
xmlhttp.open("GET","/example/xmle/books.xml",true);
xmlhttp.send();
}
```

其中url对应数据文件 http://www.w3school.com.cn/example/xmle/books.xml：

```xml
!--   Copyright w3school.com.cn  -->
<!--  W3School.com.cn bookstore example  -->
<bookstore>
	<book category="children">
		<title lang="en">Harry Potter</title>
		<author>J K. Rowling</author>
		<year>2005</year>
		<price>29.99</price>
	</book>
	<book category="cooking">
		<title lang="en">Everyday Italian</title>
		<author>Giada De Laurentiis</author>
		<year>2005</year>
		<price>30.00</price>
	</book>
	<book category="web" cover="paperback">
		<title lang="en">Learning XML</title>
		<author>Erik T. Ray</author>
		<year>2003</year>
		<price>39.95</price>
	</book>
	<book category="web">
		<title lang="en">XQuery Kick Start</title>
		<author>James McGovern</author>
		<author>Per Bothner</author>
		<author>Kurt Cagle</author>
		<author>James Linn</author>
		<author>Vaidyanathan Nagarajan</author>
		<year>2003</year>
		<price>49.99</price>
	</book>
</bookstore>
```

##### onreadystatechange 事件

当请求被发送到服务器时，我们需要执行一些基于响应的任务。

每当 readyState 改变时，就会触发 onreadystatechange 事件。

readyState 属性存有 XMLHttpRequest 的状态信息。

下面是 XMLHttpRequest 对象的三个重要的属性：

| 属性                 | 描述                                       |
| ------------------ | ---------------------------------------- |
| onreadystatechange | 存储函数（或函数名），每当 readyState 属性改变时，就会调用该函数。  |
| readyState         | 存有 XMLHttpRequest 的状态。从 0 到 4 发生变化。0: 请求未初始化；1: 服务器连接已建立；2: 请求已接收；3: 请求处理中；4: 请求已完成，且响应已就绪。 |
| status             | 200: "OK"；404: 未找到页面                     |

在 onreadystatechange 事件中，我们规定当服务器响应已做好被处理的准备时所执行的任务。

当 **readyState 等于 4 且状态为 200 时**，表示响应已就绪：

```javascript
xmlhttp.onreadystatechange=function()
  {
  if (xmlhttp.readyState==4 && xmlhttp.status==200)
    { document.getElementById("myDiv").innerHTML=xmlhttp.responseText;
    }
  }
```

> onreadystatechange 事件被触发 5 次（0 - 4），对应着 readyState 的每个变化

**使用 Callback 函数**

callback 函数是一种以参数形式传递给另一个函数的函数。

如果您的网站上存在多个 AJAX 任务，那么您应该为创建 XMLHttpRequest 对象编写一个**标准**的函数，并为每个 AJAX 任务调用该函数。

该函数调用应该包含 URL 以及发生 onreadystatechange 事件时执行的任务（每次调用可能不尽相同）：

```javascript
var xmlhttp;
function loadXMLDoc(url,cfunc)
{
if (window.XMLHttpRequest)
  {// code for IE7+, Firefox, Chrome, Opera, Safari
  xmlhttp=new XMLHttpRequest();
  }
else
  {// code for IE6, IE5
  xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
  }
xmlhttp.onreadystatechange=cfunc;
xmlhttp.open("GET",url,true);
xmlhttp.send();
}
function myFunction()
{
loadXMLDoc("/ajax/test1.txt",function()
  {
  if (xmlhttp.readyState==4 && xmlhttp.status==200)
    {
    document.getElementById("myDiv").innerHTML=xmlhttp.responseText;
    }
  });
}
```

#### AJAX实例

##### AJAX 数据库实例

当用户在上面的下拉列表中选择某个客户时，会执行名为 "showCustomer()" 的函数。该函数由 "onchange" 事件触发：

```javascript
function showCustomer(str)
{
var xmlhttp;
if (str=="")
  {
  document.getElementById("txtHint").innerHTML="";
  return;
  }
if (window.XMLHttpRequest)
  {// code for IE7+, Firefox, Chrome, Opera, Safari
  xmlhttp=new XMLHttpRequest();
  }
else
  {// code for IE6, IE5
  xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
  }
xmlhttp.onreadystatechange=function()
  {
  if (xmlhttp.readyState==4 && xmlhttp.status==200)
    {
    document.getElementById("txtHint").innerHTML=xmlhttp.responseText;
    }
  }
xmlhttp.open("GET","getcustomer.asp?q="+str,true);
xmlhttp.send();
}
```

showCustomer() 函数执行以下任务：

- 检查是否已选择某个客户
- 创建 XMLHttpRequest 对象
- 当服务器响应就绪时执行所创建的函数
- 把请求发送到服务器上的文件
- 请注意我们向 URL 添加了一个参数 q （带有输入域中的内容）

**AJAX 服务器页面**

由上面的 JavaScript 调用的服务器页面是 ASP 文件，名为 "getcustomer.asp"。

用 PHP 编写服务器文件也很容易，或者用其他服务器语言。请看[用 PHP 编写的相应的例子](http://www.w3school.com.cn/php/php_ajax_database.asp)。

"getcustomer.asp" 中的源代码负责对数据库进行查询，然后用 HTML 表格返回结果：

##### AJAX ASP/PHP 请求实例

当用户在上面的输入框中键入字符时，会执行函数 "showHint()" 。该函数由 "onkeyup" 事件触发：

```javascript
function showHint(str)
{
var xmlhttp;
if (str.length==0)
  {
  document.getElementById("txtHint").innerHTML="";
  return;
  }
if (window.XMLHttpRequest)
  {// code for IE7+, Firefox, Chrome, Opera, Safari
  xmlhttp=new XMLHttpRequest();
  }
else
  {// code for IE6, IE5
  xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
  }
xmlhttp.onreadystatechange=function()
  {
  if (xmlhttp.readyState==4 && xmlhttp.status==200)
    {
    document.getElementById("txtHint").innerHTML=xmlhttp.responseText;
    }
  }
xmlhttp.open("GET","gethint.asp?q="+str,true);
xmlhttp.send();
}
```

如果输入框为空 (str.length==0)，则该函数清空 txtHint 占位符的内容，并退出函数。

如果输入框不为空，showHint() 函数执行以下任务：

- 创建 XMLHttpRequest 对象
- 当服务器响应就绪时执行函数
- 把请求发送到服务器上的文件
- 请注意我们向 URL 添加了一个参数 q （带有输入框的内容）

##### AJAX XML 实例

当用户点击上面的“获得 CD 信息”这个按钮，就会执行 loadXMLDoc() 函数。

loadXMLDoc() 函数创建 XMLHttpRequest 对象，添加当服务器响应就绪时执行的函数，并将请求发送到服务器。

当服务器响应就绪时，会构建一个 HTML 表格，从 XML 文件中提取节点（元素），最后使用已经填充了 XML 数据的 HTML 表格来更新 txtCDInfo 占位符：

```javascript
function loadXMLDoc(url)
{
var xmlhttp;
var txt,xx,x,i;
if (window.XMLHttpRequest)
  {// code for IE7+, Firefox, Chrome, Opera, Safari
  xmlhttp=new XMLHttpRequest();
  }
else
  {// code for IE6, IE5
  xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
  }
xmlhttp.onreadystatechange=function()
  {
  if (xmlhttp.readyState==4 && xmlhttp.status==200)
    {
    txt="<table border='1'><tr><th>Title</th><th>Artist</th></tr>";
    x=xmlhttp.responseXML.documentElement.getElementsByTagName("CD");
    for (i=0;i<x.length;i++)
      {
      txt=txt + "<tr>";
      xx=x[i].getElementsByTagName("TITLE");
        {
        try
          {
          txt=txt + "<td>" + xx[0].firstChild.nodeValue + "</td>";
          }
        catch (er)
          {
          txt=txt + "<td> </td>";
          }
        }
    xx=x[i].getElementsByTagName("ARTIST");
      {
        try
          {
          txt=txt + "<td>" + xx[0].firstChild.nodeValue + "</td>";
          }
        catch (er)
          {
          txt=txt + "<td> </td>";
          }
        }
      txt=txt + "</tr>";
      }
    txt=txt + "</table>";
    document.getElementById('txtCDInfo').innerHTML=txt;
    }
  }
xmlhttp.open("GET",url,true);
xmlhttp.send();
}
```

#### jQuery AJAX 

##### jQuery load() 方法

jQuery load() 方法是简单但强大的 AJAX 方法。

load() 方法从服务器加载数据，并把返回的数据放入被选元素中。

```javascript
$(selector).load(URL,data,callback);
```

必需的 **URL** 参数规定您希望加载的 URL。

可选的 **data** 参数规定与请求一同发送的查询字符串键/值对集合。

可选的 **callback** 参数是 load() 方法完成后所执行的函数名称。

```javascript
//把文件 "demo_test.txt" 的内容加载到指定的 <div> 元素中
$("#div1").load("demo_test.txt");

//把 jQuery 选择器添加到 URL 参数(把 "demo_test.txt" 文件中 id="p1" 的元素的内容，加载到指定的 <div> 元素中)
$("#div1").load("demo_test.txt #p1");
```

可选的 callback 参数规定当 load() 方法完成后所要允许的回调函数。回调函数可以设置不同的参数：

- *responseTxt* - 包含调用成功时的结果内容
- *statusTXT* - 包含调用的状态
- *xhr* - 包含 XMLHttpRequest 对象

```javascript
//下面的例子会在 load() 方法完成后显示一个提示框。如果 load() 方法已成功，则显示“外部内容加载成功！”，而如果失败，则显示错误消息：
$("button").click(function(){
  $("#div1").load("demo_test.txt",function(responseTxt,statusTxt,xhr){
    if(statusTxt=="success")
      alert("外部内容加载成功！");
    if(statusTxt=="error")
      alert("Error: "+xhr.status+": "+xhr.statusText);
  });
});
```

##### AJAX get() 和 post()

###### HTTP 请求

两种在客户端和服务器端进行请求-响应的常用方法是：**GET 和 POST**。

- ***GET*** - 从指定的资源请求数据

  请注意，查询字符串（名称/值对）是在 GET 请求的 URL 中发送的：

  ```javascript
  /test/demo_form.asp?name1=value1&name2=value2
  ```

  有关 GET 请求的其他一些注释：

  - GET 请求可被缓存
  - GET 请求保留在浏览器历史记录中
  - GET 请求可被收藏为书签
  - GET 请求不应在处理敏感数据时使用
  - GET 请求有长度限制
  - GET 请求只应当用于取回数据

- ***POST*** - 向指定的资源提交要处理的数据

  请注意，查询字符串（名称/值对）是在 POST 请求的 HTTP 消息主体中发送的：

  ```javascript
  POST /test/demo_form.asp HTTP/1.1
  Host: w3schools.com
  name1=value1&name2=value2
  ```

  有关 POST 请求的其他一些注释：

  - POST 请求不会被缓存
  - POST 请求不会保留在浏览器历史记录中
  - POST 不能被收藏为书签
  - POST 请求对数据长度没有要求

**其他 HTTP 请求方法**

下面的表格列出了其他一些 HTTP 请求方法：

| 方法      | 描述                             |
| ------- | ------------------------------ |
| HEAD    | 与 GET 相同，但只返回 HTTP 报头，不返回文档主体。 |
| PUT     | 上传指定的 URI 表示。                  |
| DELETE  | 删除指定资源。                        |
| OPTIONS | 返回服务器支持的 HTTP 方法。              |
| CONNECT | 把请求连接转换到透明的 TCP/IP 通道。         |

###### jQuery $.get() 方法

$.get() 方法通过 HTTP GET 请求从服务器上请求数据。

语法

```javascript
$(selector).get(url,data,success(response,status,xhr),dataType)
```

| 参数                             | 描述                                       |
| ------------------------------ | ---------------------------------------- |
| *url*                          | 必需。规定将请求发送的哪个 URL。                       |
| *data*                         | 可选。规定连同请求发送到服务器的数据。                      |
| *success(response,status,xhr)* | 可选。规定当请求成功时运行的函数。额外的参数：response - 包含来自请求的结果数据；status - 包含请求的状态；xhr - 包含 XMLHttpRequest 对象 |
| *dataType*                     | 可选。规定预计的服务器响应的数据类型。默认地，jQuery 将智能判断。可能的类型："xml""html""text""script""json""jsonp" |

该函数是简写的 Ajax 函数，等价于：

```javascript
$.ajax({
  url: url,
  data: data,
  success: success,
  dataType: dataType
});
```

根据响应的不同的 MIME 类型，传递给 success 回调函数的返回数据也有所不同，这些数据可以是 XML root 元素、文本字符串、JavaScript 文件或者 JSON 对象。也可向 success 回调函数传递响应的文本状态。

对于 jQuery 1.4，也可以向 success 回调函数传递 XMLHttpRequest 对象。

下面的例子使用 $.get() 方法从服务器上的一个文件中取回数据：

```javascript
$("button").click(function(){
  $.get("demo_test.asp",function(data,status){
    alert("Data: " + data + "\nStatus: " + status);
  });
});
//$.get() 的第一个参数是我们希望请求的 URL（"demo_test.asp"）。
//第二个参数是回调函数。第一个回调参数存有被请求页面的内容，第二个回调参数存有请求的状态。
```

 ASP 文件 ("demo_test.asp") 类似这样：

```asp
<%response.write("This is some text from an external ASP file.")%>
```

###### jQuery $.post() 方法

post() 方法通过 HTTP POST 请求从服务器载入数据。

语法

```javascript
$.post(url,data,success(data, textStatus, jqXHR),dataType)
```

| 参数                                 | 描述                                       |
| ---------------------------------- | ---------------------------------------- |
| *url*                              | 必需。规定把请求发送到哪个 URL。                       |
| *data*                             | 可选。映射或字符串值。规定连同请求发送到服务器的数据。              |
| *success(data, textStatus, jqXHR)* | 可选。请求成功时执行的回调函数。                         |
| *dataType*                         | 可选。规定预期的服务器响应的数据类型。默认执行智能判断（xml、json、script 或 html）。 |

该函数是简写的 Ajax 函数，等价于：

```
$.ajax({
  type: 'POST',
  url: url,
  data: data,
  success: success,
  dataType: dataType
});
```

根据响应的不同的 MIME 类型，传递给 success 回调函数的返回数据也有所不同，这些数据可以是 XML 根元素、文本字符串、JavaScript 文件或者 JSON 对象。也可向 success 回调函数传递响应的文本状态。

对于 jQuery 1.5，也可以向 success 回调函数传递 [jqXHR 对象](http://www.w3school.com.cn/jquery/ajax_post.asp#jqxhr_object)（jQuery 1.4 中传递的是 XMLHttpRequest 对象）。

下面的例子使用 $.post() 连同请求一起发送数据：

```javascript
$("button").click(function(){
  $.post("demo_test_post.asp",
  {
    name:"Donald Duck",
    city:"Duckburg"
  },
  function(data,status){
    alert("Data: " + data + "\nStatus: " + status);
  });
});
```

$.post() 的第一个参数是我们希望请求的 URL ("demo_test_post.asp")。

然后我们连同请求（name 和 city）一起发送数据。

"demo_test_post.asp" 中的 ASP 脚本读取这些参数，对它们进行处理，然后返回结果。

第三个参数是回调函数。第一个回调参数存有被请求页面的内容，而第二个参数存有请求的状态

ASP 文件 ("demo_test_post.asp") 类似这样：

```asp
<%dim fname,city
fname=Request.Form("name")
city=Request.Form("city")
Response.Write("Dear " & fname & ". ")
Response.Write("Hope you live well in " & city & ".")%>
```

###### getJSON() 方法

通过 HTTP GET 请求载入 JSON 数据。

在 jQuery 1.2 中，您可以通过使用 JSONP 形式的回调函数来加载其他网域的 JSON 数据，如 "myurl?callback=?"。jQuery 将自动替换 ? 为正确的函数名，以执行回调函数。 注意：此行以后的代码将在这个回调函数执行前执行。

语法

```javascript
jQuery.getJSON(url,data,success(data,status,xhr))
```

| 参数                         | 描述                                       |
| -------------------------- | ---------------------------------------- |
| *url*                      | 必需。规定将请求发送的哪个 URL。                       |
| *data*                     | 可选。规定连同请求发送到服务器的数据。                      |
| *success(data,status,xhr)* | 可选。规定当请求成功时运行的函数。额外的参数：*response* - 包含来自请求的结果数据*status* - 包含请求的状态*xhr* - 包含 XMLHttpRequest 对象 |

详细说明

该函数是简写的 Ajax 函数，等价于：

```javascript
$.ajax({
  url: url,
  data: data,
  success: callback,
  dataType: json
});
```

发送到服务器的数据可作为查询字符串附加到 URL 之后。如果 *data* 参数的值是对象（映射），那么在附加到 URL 之前将转换为字符串，并进行 URL 编码。

传递给 *callback* 的返回数据，可以是 JavaScript 对象，或以 JSON 结构定义的数组，并使用 $.parseJSON() 方法进行解析(从jQuery 3.0开始，不推荐使用$.parseJSON。 要解析JSON字符串，请改用原生的 JSON.parse 方法).

