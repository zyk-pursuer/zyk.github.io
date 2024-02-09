# HTML学习教程
## 1.VSCode常用命令
    ctrl+alt+f: 代码格式化
    shift+alt+up/down：快速复制一行代码
    alt+up/down：向上/下移动一行
## 2.标签
### 2.1标题标签
    <h1></h1>到<h6></h6>分别对应一级标题到六级标题
    h$*6可以快速生成一到六级标题
    标签中可以添加属性align="left|center|right"来调整对应位置
### 2.2段落标签
    <p></p>产生一个新段落
    <br/>在不产生新段落的情况下进行换行
    <hr color="" width="" size="" align="">设置水平线及其颜色、长度、宽度和位置
### 2.3图片标签
    <img src="" alt="" width="" height="" title=""/>分别设置图片的名称或路径、替代
    文字、宽度、高度及提示语。其中图片路径可以分为绝对路径、相对路径和网络路径。绝对路
    径即图片的具体存储位置；相对路径可分为父级关系、子级关系和同级关系，分别以../、/、
    ./（可省略）显示；网络路径即具体的网址。img标签还可以添加float属性使得文字环绕图片，左对齐或右对齐。
### 2.4超文本链接标签
    <a href="url">文本或图片</a>
### 2.5文本标签
    <em></em>、<b></b>、<i></i>、<strong></strong>、<del></del>、<span></span>分
    别代表着重、粗体、斜体、加强、删除、无特定含义。<sub></sub><sup></sup>分别代表下标和上标。
    <pre></pre>会保持原来的换行和空格，但最好不要包裹块级元素。
### 2.6列表标签
    <ol><li></li></ol>表示有序列表，ol可以设置属性type="1|a|A|i|I"，分别代表以阿拉
    伯数字、小写字母、大写字母、小写罗马字母、大写罗马字母排序。有序列表支持嵌套。
    <ul><li></li></ul>表示无序列表，ul可以设置属性type="disc|circle|square|none"，
    分别代表实心圆、空心圆、小方块、无。无序列表同样支持嵌套。ul>li*x可以快速生成x级列表。
    <dl><dt></dt><dd></dd></dl>表示定义列表，dt与dd交替出现可以表示交替缩进和凸出。
### 2.7表格标签
    <table></table><tr></tr><td></td>分别代表表格、行、单元格。table>tr*x>td*y{z}
    可以快速生成x行y列内容为z的表格。table可以设置属性border、width、height来分别代
    表表格边界、宽度和高度。
    单元格水平和垂直合并分别用colspan和rowspan来表示。
## 3.表单
    <form action="url" method="get|post" name="myform"></form>中action为服务器地址，
    name为表单名称。
    表单元素包括表单标签、表单域和表单按钮：
    <form><input type="text"><input type="password"><input type="submit"></form>。
## 4.元素
    元素可以分为块级元素和内联元素。
|块级元素|内联元素|
|---|---|
|页面中独占一行（自上到下垂直排列）|只占自身大小|
|可以设置width和height|不能设置|
|可以包含块级元素和内联元素|只能包含内联元素|
    常见块级元素：div,form,h1-h6,hr,p,table,ul等
    常见内联元素：a,b,em,i,span,strong等
    行内块级元素：button,img,input等
## 5.HTML5新增内容
    HTML5新增语义化内容。HTML:<div id="header"></div>;HTML5:<header></header>。
    HTML5标签：<header><nav><aside><article><section><footer>。
