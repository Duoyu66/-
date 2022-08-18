## 前端开始
## 标签

 1.

1.标题标签分为6个等级<h1>到<h6>h是head的缩写，重要性递减
2.段落标签<p>我是一个段落标签</p>
3.换行标签<br />（强制换行）特点:是一个单标签，不会分段落，仅仅强制换行
4.加粗<strong></strong> 或<b></b>
5.倾斜<em></em>或<i></i>
6..删除线<del></del>或<s></s>
7.下划线<ins></ins>或<u></u>
8.<div>和<span>是没有语义的，它们就是一个盒子，用来装内容的<div>这是头部</div>   <span>今日价格</span>
div是divison的缩写，表示分割，分区。span意为跨度，跨距
特点:<div>标签用来布局,但是现在一行只能放一个<div>大盒子
<span>标签用来布局,一行可以多个<span>小盒子
9.图像标签<img src="图像URL"/>  单标签 src是<img>标签的必须属性
titile 鼠标放在图片可以显示文字(提示) alt：图片不能正常放出显示的文字(替换)
width 宽(像素) higth 高
border 边框
特点:各个属性部分顺序,标签名与属性，属性之间均以空格分开
图像标签可以拥有多个属性，必须卸载标签名的后面
属性采取键值对的格式，即key=“value”的格式，属性=“属性值”
10.根目录:打开目录的第一层就是根目录
11.<label for="sex">男</label>
<input type="radio" name="sex" id="sex">
name是为了多选一
label是为了点击文字可以选择
12.超链接标签:#
# 知识点
div*3 Tab生成多个div
ul>li 父子关系
div+p 并列关系
.demo$*5自增五个
div{＄}*5
## 外部链接
<a href="跳转目标" target=''目标窗口的弹出方式" >文本或图像</a>
_blank 新的窗口打开 _self还是这个窗口打开
## 内部链接:
不需要http://
herf="#" 空链接
## 下载链接
herf="压缩包"
## 锚点链接
<a href="#123"></a>
<h1 id="123></h1>
## 注释
使用方法  <!--  注释文字-->
## 特殊字符
&nbsp; 空格
&lt; 小于号
&gt;大于号
## 表格
<table>
<thead> <th></th></thead>
<tbody></tbody>
</table>
## 列表
1.无序列表<ul></ul>里面只能包含li，没有顺序，使用较多。li可以包含任何标签
2.有序标签<ol></ol>有序标签里面只能包含li，有顺序，使用相对较少。li里面可以包含任何标签
3.自定义标签 <dl></dl>自定义列表 里面只能包含dt和dd dt和dd里面可以放任何标签
## 表单
用来收集信息
表单的组成:表单域，表单控件，提示信息三部分组成。
<form>标签用于定义表单域，以实现用户信息的收集和传递
## 类选择器
样式点定义,结构类(class)调用,一个或多个，开发最常用
## 字体
font: font-style font-weight font-size/line-height font-family
size和family不能省略
text-align :center;居中对齐
left左对齐
right右对齐
text-decoration装饰文本:none 默认没有装饰线
underline下划线 (终点)
overline上划线
line-througth删除线
## 缩进
text-indent 使文本的第一行缩进多少距离
text-indent=2em; em是一个相对单位，是缩进当前一个文字的单位。
## 行间距
line-height 行间距
## CSS引入方式
1.行内样式表
<div style="color:red;font-size:12px;">青春不常在，抓紧谈恋爱</div>
2.内部样式表
放在head的内部style的里面
3.外部样式表
快速生成css： w200 可以生成width:200px;
lh26 可以生成line-height:26px;
## css的复合器
1.后代选择器(包含选择器):

```html
<head>
    <meta charset="UTF-8">
    <title>品优购</title>
    <link rel="stylesheet" href="style.css">
    <style>
        ul li {
            color: pink;
        }
    </style>
</head>
<body>
<ol>
    <li>我是ol的孩子</li>
    <li>我是ol的孩子</li>
    <li>我是ol的孩子</li>
</ol>
<ul>
    <li>我是ul得到孩子</li>
    <li>我是ul得到孩子</li>
    <li>我是ul得到孩子</li>
</ul>
```
元素1 元素2{
	样式声明
	}
	元素1和元素2中间用空格隔开
	元素1是父级，元素2是子集即，最终选择的是元素2
	元素2可以是儿子，也可以是孙子等，只要是元素1的后代即可
2.子选择器:

```html
      .nav > a {
            color: yellow;
        }
```
注意>号，表示只选择亲儿子
3.并集选择器:
并集选择器可以选择多组标签，同时为他们定义相同的样式。通常用于集体声明
任何选择器都可以作为并集选择器的一部分
div,p{
} 
用逗号分割,可以理解为div和p
4.伪类选择器:
使鼠标经过时显示颜色
a:link /*选择所有为被访问的链接*/
a:visited /*选择所有已被访问的链接*/
a:hover/*选择鼠标位于其上得到链接*/
a:active/*选择活动链接(鼠标正在按下，还未弹起的链接)*/
顺序尽量不要颠倒
因为a链接在浏览器中具有默认样式，所以我们实际工作中需要给链接单独指定样式。
我们经常这么用:

```html
  a {
            color: black;
        }
   a:hover {
            color: red;
        }
```
focus伪类选择器:
input:focus{
	background-color:red;  改变光标选中的背景色
	color:red; 改变向其输入的文字的颜色
}
## 元素的显示模式

html元素一般分为块元素(div)和行内元素(span).
块元素:
h1-h6 p div ul ol li
1.比较霸道，自己独占一行
2.高度，宽度，内外边距都可以控制
3.宽度默认是容器(父级)的100%
4.是一个容器及盒子，里面可以放行内或者块级元素
注意:文字类的元素内不能使用块级元素
p标签主要用于存放文字，因此p里面不能放块级元素，特别是不饿能放div
同理 ，h1-h6等都是 文字类块级标签，里面也不能放其他块级元素
行内元素：
a strong b em i del s ins u span
特点:
1.相邻行内元素在一行上，一行可以显示多个
2.高、宽直接设置是无效的。
3.默认宽度就是它本身内容的宽度
4.行内元素只能容纳文本或其他行内元素

> 链接里不能再放链接

a可以放块级元素，但是给<a>转换下会计模式最安全

 1. 行内元素转化为块内元素:display:block;
 2. 块内元素转化为行内元素:display:inline
 3. 转成行内块display:iniline-block


 垂直居中的解决方案:让文字的高度等于盒子的高度。

 4. 背景图片的好处:非常便于控制位置
 5. background-image:url("路径");
 6. backgrrount-repeat:平铺的方式
 7. repeat默认的平铺
 8. no-repeat 背景图像不平铺
 9. repeat-x沿着x平铺
 10. 页面元素既可以添加背景颜色和背景图片，不过图片会压住背景颜色
 11. background-attachment：scroll 默认为滚动
 12. fixed 背景图象固定
 13. 背景的复合型写法背景颜色，背景图片地址，背景平铺，背景图像滚动，背景图片位置
网页布局的过程:
 1.先准备好相关的网页元素，网页元素基本都是盒子Box
 2.利用CSS设置好盒子样式，然后摆放到相应位置
 3.往盒子里面装内容
 核心本质:利用CSS摆盒子
## 两种引入
<script type="text/javascript" src="jj.js"></script> 引入js
    <link rel="stylesheet" href="k.css">  引入css
## 边框
solid 实线边框
dashed 长虚线边框
dotted 点边框
hidden 隐藏
border:1px solid red;没有先后顺序
 border: blue solid 1px;
            border-top:1px solid red; border 的层叠性
border-collapse 合并边框
如果盒子本身没有指定高度和宽度，则padding不会撑大盒子
外边距可以让块级盒子水平居中，但是满足两个条件:
1.盒子必须指定了宽度
2.盒子左右的外边距都设置auto
解决边框塌陷问题:
1.可以为父元素定义上边框
2.可以为父元素定义上内边距
3.可以为父元素添加oveflow:hidden
清除内外边距:
*{
	padding:0;
	margin:0;
}
行内元素为了照顾兼容性，尽量值设置左右内外边距，不要设置上下内外边距。但是转换为块级和行内块元素就可以了。
margin：top right bottom left(上右下左)
inline 是一行放多个
block 是一行放一个
## 去掉列表前的小圆点
  li {
            /* 去掉li前面的小圆点 */
            list-style: none;
        }
## 圆角边框
border-radius
## 浮动
传统网页布局的三种方式:
1.普通流
2.浮动
3.定位
多个块级元素纵向排列找标准流，多个块级元素横向排列找浮动
浮动：属性用于创建浮动框，将其移动到另一边，直到左边缘或右边缘初级包含块会另一个浮动框的边缘
只有左浮或者右浮
浮动的特性:
1.浮动的元素会脱离标准流(脱标)
2.浮动的元素会一行内下那是并且元素顶部对齐
3.浮动的元素会具有行内块元素的特性
如果行内元素有了浮动，则不需要转换为块级/行内块级元素就可以直接给高度和宽度
为了约束浮动元素位置，我们网页布局一般采取的策略是:先用标准流的父元素排列上下位置，之后内部子元素采取浮动排列左右位置，符合网页布局第一准则。
## 使用列表时要清除内外边距
## 清除浮动-额外标签法
优点：通俗易懂，书写方便
缺点:添加许多无意义的标签，结构化较差
要求这个新的空标签必须是块级元素
为什么要清除浮动:1.父级没高度
2.子盒子浮动了
3.影响下面布局了，我们就应该清除浮动了
## CSS属性书写顺序
1.布局定位属性
2.自身属性
3.文本属性
4.其他属性
## 实际开发时的小技巧
 14. 实际开发中，我们不会直接用链接a而是用li包含链接（li+a）的做法
## 定位
定位=定位模式+边偏移
定位模式用于指定一个元素在文档中的定位方式。边偏移则决定了该元素的最终位置。
## 知识点
 15. resize:none;使文本框不能拖拽
 16. outline:0;去除表单轮廓

## 单行超出省略号显示
white-space:nowrap;强制不换行
overflow:hidden;隐藏溢出的
text-overflow:ellipsis;结尾省略号显示
![在这里插入图片描述](https://img-blog.csdnimg.cn/0a571062699d41608599ef6d273dd420.png)

## 多行省略号显示
![在这里插入图片描述](https://img-blog.csdnimg.cn/02977205cc594b6ab017077705a99d5a.png)

## 初始化
![](https://img-blog.csdnimg.cn/4ada590f50ca4e3c8a581389be08e6ee.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/a62e77004c5a4b2aafddcf61db969d02.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/d64b05eb6f644ba7bdedad37cb1233bb.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/d62cbaa3b0254ba99bb5fd3d65d05818.png)
![](https://img-blog.csdnimg.cn/57eadff9ee5240ce89c59c2565d5682e.png)
section div:nth-child(1){}
nth-child会把所有的盒子都排列序号，执行的时候首先看:nth-child(1)之后看 前面div(先把第一i个选出来，再看匹不匹配)
section div:nth-of-type(1)会把指定的元素的盒子排列序号，在选择第一个孩子权重为12{：nth-of-type(1)10  div 1 section 1 12=10+1+1}


## 类选择器ii，属性选择器,伪类选择器权重都是10

 1. ul li:first-child{}ul中的li的第一个
 2. ul li:first-child{}ul中li的第一个
 3. ul li:nth-chil(n)ul中li的第n个 //n可以是数字，关键字和公式 even 偶数odd 奇数  
 4. n+5从第五个开始（包含的第五个）到最后
 5. -n+5前五个(包含第五个)
**![加粗样式](https://img-blog.csdnimg.cn/a65ca1c363e5432296e97703f2428f32.png)
**
![在这里插入图片描述](https://img-blog.csdnimg.cn/ffeec4170bc54bccbcea8d62e209aa87.png)
trnsform不会影响其他盒子位置
![在这里插入图片描述](https://img-blog.csdnimg.cn/b41061b81a174fa49c94e28c30a94050.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/70d24284d5094559a896edb5ff2a8eac.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/29509633dad24f2493da82383b472180.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/31a3679920ac45b8bb230838f2cbbd03.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/11dda5d617994b4bb9810e947a224dc0.png)