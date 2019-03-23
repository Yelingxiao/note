## CSS&LESS

* [**CSS的盒子模型**](#CSS的盒子模型)
* [**CSS选择器**](#CSS选择器)
* [**水平居中**](#水平居中)
* [**水平垂直居中**](#水平垂直居中)
* [**position定位**](#position定位)
* [**BFC规范**](#BFC规范)
* [**CSS优化、提高性能的方法**](#CSS优化、提高性能的方法)
* [**css画图形**](#css画图形)





#### CSS的盒子模型

标准盒子模型：宽度=内容的宽度（content）+ border + padding + margin

低版本IE盒子模型：宽度=内容宽度（content+border+padding）+ margin

 **box-sizing属性**

用来控制元素的盒子模型的解析模式，默认为content-box
context-box：W3C的标准盒子模型，设置元素的 height/width 属性指的是content部分的高/宽

border-box：IE传统盒子模型。设置元素的height/width属性指的是border + padding + content部分的高/宽

[[↑] 回到顶部](#CSS&LESS)

#### CSS选择器

1. **基本选择器**

| **选择器**  | **含义**                                       |
| :---------- | ---------------------------------------------- |
| *****       | 通用元素选择器，匹配任何元素                   |
| **E**       | 标签选择器，匹配所有使用E标签的元素            |
| **.info**   | class选择器，匹配所有class属性中包含info的元素 |
| **#footer** | id选择器，匹配所有id属性等于footer的元素       |

2. **多元素的组合选择器**

| **选择器** | 含义                                                         |
| ---------- | ------------------------------------------------------------ |
| E,F        | 多元素选择器，同时匹配所有E元素或F元素，E和F之间用逗号分隔   |
| E F        | 后代元素选择器，匹配所有属于E元素后代的F元素，E和F之间用空格分隔 |
| E > F      | 子元素选择器，匹配所有E元素的子元素F                         |
| E + F      | 毗邻元素选择器，匹配所有紧随E元素之后的同级元素F             |

3. **属性选择器**

| 选择器       | 含义                                                         |
| ------------ | ------------------------------------------------------------ |
| E[att]       | 匹配所有具有att属性的E元素，不考虑它的值。（注意：E在此处可以省略，比如"[cheacked]"。以下同。） |
| E[att=val]   | 匹配所有att属性等于"val"的E元素                              |
| E[att~=val]  | 匹配所有att属性具有多个空格分隔的值、其中一个值等于"val"的E元素 |
| E[att\|=val] | 匹配所有att属性具有多个连字号分隔（hyphen-separated）的值、其中一个值以"val"开头的E元素，主要用于lang属性，比如"en"、"en-us"、"en-gb"等等 |

4. **伪类**

![image-20190323193629652](/Users/yelingxiao/Library/Application Support/typora-user-images/image-20190323193629652.png)

**CSS3新增伪类**

p:first-of-type 选择属于其父元素的首个元素
p:last-of-type 选择属于其父元素的最后元素
p:only-of-type 选择属于其父元素唯一的元素
p:only-child 选择属于其父元素的唯一子元素
p:nth-child(2) 选择属于其父元素的第二个子元素
:enabled :disabled 表单控件的禁用状态。
:checked 单选框或复选框被选中。



5. **伪元素**

| 选择器              | 含义                                                         |
| ------------------- | ------------------------------------------------------------ |
| **E::after**        | 在E元素之后插入生成的内容                                    |
| **E::before**       | 在E元素之前插入生成的内容                                    |
| **E::first-letter** | 匹配E元素的第一个字母                                        |
| **E::first-line**   | 匹配E元素的第一行                                            |
| **E::backdrop**     | 是在任何处于[全屏模式](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API)的元素下的即刻渲染的盒子（并且在所有其他在堆中的层级更低的元素之上） |
| **E::selection**    | CSS伪元素应用于文档中被用户高亮的部分（比如使用鼠标或其他选择设备选中的部分）。 |

可继承的属性：font-size, font-family, color

不可继承的样式：border, padding, margin, width, height

优先级（就近原则）：!important > [ id > class > tag ] 
!important 比内联优先级高

元素选择符： 1
class选择符： 10
id选择符：100
元素标签：1000

1. !important声明的样式优先级最高，如果冲突再进行计算。
2. 如果优先级相同，则选择最后出现的样式。
3. 继承得到的样式的优先级最低。

[[↑] 回到顶部](#CSS&LESS)

#### 水平居中

1. 行内元素水平居中

这里行内元素是指文本text、图像img、按钮超链接等，只需给父元素设置text-align:center即可实现。

```css
.center {
 		text-align:center;
}
<div class="center">水平居中</div>
```

2. 块级元素水平居中

   2.1 **定宽块级元素水平居中**

只需给需要居中的块级元素加margin:0 auto即可，**但这里需要注意的是，这里块状元素的宽度width值一定要有**

```css
  .center{
      width:200px;
      margin:0 auto;
      border:1px solid red;
  }
  <div class="center">水平居中</div>
```

​	2.2 **不定宽块级元素水平居中**

不定宽，即块级元素宽度不固定
**方法1：设置table**

```css
.center{
      display:table;
      margin:0 auto;
      border:1px solid red;
  }
  <div class="center">水平居中</div>
```

**方法2：设置inline-block**（多个块状元素）

```css
  .center{
      text-align:center;
  }
  .inlineblock-div{
      display:inline-block;
  }
  <div class="center">
      <div class="inlineblock-div">1</div>
      <div class="inlineblock-div">2</div>
  </div>


```

**方法3：设置flex布局**

```css
  .center{
      display:flex;
      justify-content:center;
  }
  <div class="center">
      <div class="flex-div">1</div>
      <div class="flex-div">2</div>
  </div>

```

**方法4：position + 负margin**
**方法5：position + margin：auto**
**方法6：position + transform；**

[[↑] 回到顶部](#CSS&LESS)



#### 水平垂直居中

**方法1：绝对定位+margin:auto**

```css
   div{
        width: 200px;
        height: 200px;
     
        position:absolute;
        left:0;
        top: 0;
        bottom: 0;
        right: 0;
        margin: auto;
    }
```

**方法2：绝对定位+负margin**

```css
    div{
        width:200px;
        height: 200px;
      
        position: absolute;
        left:50%;
        top:50%;
        margin-left:-100px;
        margin-top:-100px;
    }
```

**方法3：绝对定位+transform**

```css
    div{
        width: 200px;
        height: 200px;
        
        position:absolute;
        left:50%;    /* 定位父级的50% */
        top:50%;
        transform: translate(-50%,-50%); /*自己的50% */
    }
```

**方法4：flex布局**

```css
   .box{
         height:600px;  
         
         display:flex;
         justify-content:center;  //子元素水平居中
         align-items:center;      //子元素垂直居中
           /* aa只要三句话就可以实现不定宽高水平垂直居中。 */
    }
    .box>div{
        width: 200px;
        height: 200px;
    }
```

**方法5：table-cell实现居中**

```css
.table-cell {
  			width: 200px;
        height: 200px;
        display:table-cell;
        text-align:center;
        vertical-align: middle;
	}
```

[[↑] 回到顶部](#CSS&LESS)

#### position定位

**static**: 该关键字指定元素使用正常的布局行为，即元素在文档常规流中当前的布局位置。此时 `top`, `right`, `bottom`, `left` 和 `z-index `属性无效。

**relative**: 该关键字下，元素先放置在未添加定位时的位置，再在不改变页面布局的前提下调整元素位置（因此会在此元素未添加定位时所在位置留下空白）。position:relative 对 table-*-group, table-row, table-column, table-cell, table-caption 元素无效。

**absolute**: 不为元素预留空间，通过指定元素相对于最近的非 static 定位祖先元素的偏移，来确定元素位置。绝对定位的元素可以设置外边距（margins），且不会与其他边距合并。

**fixed**: 不为元素预留空间，而是通过指定元素相对于屏幕视口（viewport）的位置来指定元素位置。元素的位置在屏幕滚动时不会改变。打印时，元素会出现在的每页的固定位置。`fixed` 属性会创建新的层叠上下文。当元素祖先的 `transform`  属性非 `none` 时，容器由视口改为该祖先。

**sticky**: 盒位置根据正常流计算(这称为正常流动中的位置)，然后相对于该元素在流中的 flow root（BFC）和 containing block（最近的块级祖先元素）定位。在所有情况下（即便被定位元素为 `table 时`），该元素定位均不对后续元素造成影响。当元素 B 被粘性定位时，后续元素的位置仍按照 B 未定位时的位置来确定。`position: sticky `对 `table` 元素的效果与 `position: relative `相同。



**position跟display、overflow、float这些特性相互叠加后会怎么样**

display属性规定元素应该生成的框的类型；position属性规定元素的定位类型；float属性是一种布局方式，定义元素在哪个方向浮动。

类似于优先级机制：position：absolute/fixed优先级最高，有他们在时，float不起作用，display值需要调整。float 或者absolute定位的元素，只能是块元素或表格。

[[↑] 回到顶部](#CSS&LESS)



#### BFC规范

**块格式化上下文（Block Formatting Context，BFC）** 是Web页面的可视化CSS渲染的一部分，是块盒子的布局过程发生的区域，也是浮动元素与其他元素交互的区域。

通俗一点来讲，可以把 BFC 理解为一个封闭的大箱子，箱子内部的元素无论如何翻江倒海，都不会影响到外部。

[MDN BFC](<https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Block_formatting_context>)

[10 分钟理解 BFC 原理](https://zhuanlan.zhihu.com/p/25321647)

[CSS 布局](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Introduction)

[[↑] 回到顶部](#CSS&LESS)



#### CSS优化、提高性能的方法

1. 避免过度约束
2. 避免后代选择符
3. 避免链式选择符
4. 使用紧凑的语法
5. 避免不必要的命名空间
6. 避免不必要的重复
7. 最好使用表示语义的名字。一个好的类名应该是描述他是什么而不是像什么
8. 避免！important，可以选择其他选择器
9. 尽可能的精简规则，你可以合并不同类里的重复规则

[[↑] 回到顶部](#CSS&LESS)

#### css画图形

**三角形**

首先，需要把元素的宽度、高度设为0。然后设置边框样式。

```css
.child{
  width: 0;
  height: 0;
  border-top: 40px solid transparent;
  border-left: 40px solid transparent;
  border-right: 40px solid transparent;
  border-bottom: 40px solid #ff0000;
}
```

[[↑] 回到顶部](#CSS&LESS)

