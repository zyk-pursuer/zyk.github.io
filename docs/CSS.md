# CSS学习教程
## 1.CSS语法
    css包括一个选择器和多个声明：<style><h1>{color:red;font-size:20px}</style>。
    选择器分为全局选择器*{}、元素选择器x{}（可以用span包围特定内容然后定义span）、
    类选择器.x{}（然后在标签里添加class="x"，class内容可以有多个，用空格隔开）、id
    选择器#x{}(在标签里添加id="x",id只能使用一次，不能以数字开头)和合并选择器（中间
    用逗号隔开）。选择器优先级以数字衡量：内联样式1000，id选择器样式100，类选择器10，
    元素选择器1。
## 2.CSS引入方式
    css引入方式分为三种：内联样式、内部样式和外部样式。
    内联样式：style="color:red;font-size:20px"
    内部样式：在head里添加style
    外部样式：新建css文件定义属性，并在head里添加<link rel="stylesheet" type="text/css"
             href="xxx.css">
## 3.CSS属性
### 3.1字体属性
    颜色有三种定义方式：red、#ff0000、rgb(255,0,0)。（rgb可以增加透明度属性变为rgba，
    透明度区间为[0,1]）。
    大小用font-size，粗细用font-weight。粗细的值可以是normal、bold（er）、lighter，
    也可以是100-700之间（400默认正常）。
    样式用font-style，值为normal或者italic。
    类型用font-family，值必须加上引号。
### 3.2背景属性
    背景属性包括background-color/-image/-position/-repeat/-size。
    position可以设置left top到right bottom共9种位置，同样也可以设置百分比或者具体数值。
    平铺方式repeat可以设置repeat（默认值）、repeat-x、repeat-y、no-repeat。
    size可以设置数值、百分比、cover（保持纵横比并填充目标区域的最小大小）和contain（保持
    纵横比并填充目标区域的最大大小）。
### 3.3文本属性
    文本属性包括text-align（left、center、right）、text-decoration（underline、
    overline、line-through）、text-transform（capitalize、uppercase、lowercase）、
    text-indent（首行缩进，允许负值）。
### 3.4表格属性
    在head里定义table{border:1px solid red;border-collapse:collapse;width:20px;height
    :20px;}。单元格内文本对齐方式：text-align和vertical-align。可以在单元格的文字和边框之
    间填充：padding。还可以设置背景颜色background-color和文本颜色color。
    表格宽度可以使用:first-child|:last-child|:nth-child(x)来设置对应列的宽度。
## 4.关系选择器
    关系选择器分为四种：后代选择器E F{}；子代选择器E>F{}；相邻兄弟选择器E+F{}；通用兄弟选择
    器E~F{}。
## 5.盒子模型
    盒子模型包括内容content、内边距padding、边框border和外边距margin。padding可以定义上下
    和左右的宽度（中间有空格）；border定义同3.4。padding和margin可以分开定义上下左右-left等
    等。
    弹性盒子模型用来更好管理盒子间的关系。在父元素上定义属性display：flex即可。其他相关属性包
    括盒子摆放顺序flex-direction:row|row-reverse|column|column-reverse、盒子换行flex-wrap:nowrap|wrap|wrap-reverse、前两者的结合flex-flow:'flex-direction' 'flex-wrap'、盒子对齐方式justify-content:flex-start|center|flex-end|space-between|space-around、纵向对齐方式align-items:flex-start|center|flex-end|stretch|baseline和多方向对齐align-content:flex-start|center|flex-end|stretch|space-between|space-around。子元素属性包括order:<integar>（数值越小越靠前）、flex-grow:<number>（默认为0，不同数值对应不同剩余空间的分配比例）、flex-shrink:<number>（默认为1，为0的子元素不缩小）、flex-basis:auto（默认为auto，可以设置具体值表示固定大小）、前三者的结合flex:none（该属性有两个值，none（0 0 auto）和auto（1 1 auto））、align-self（有6个值flex-start|center|flex-end|stretch|baseline|auto，默认auto，继承父元素，没有父元素则等同于stretch）。
## 6.文档流
    文档流是文档可显示内容在排列时所占用的位置。
    文档流存在的问题：大小不一时底端对齐；空格折叠；元素有空隙。
    解决方案：
    1.浮动float:left|right。
    浮动的副作用：使父元素高度塌陷；后续元素会受到影响。
    清除浮动的四种方案：设置父元素高度；受影响的元素增加clear:left|right|both；在父元素标签里
    设置overflow:hidden;clear:both；添加伪对象::after{container:"";display:block;clear:
    both}。
    2.定位position:relative|absolute|fixed
    绝对定位和固定定位都会脱离文档流。可以用left|right|top|bottom来定义位置。（注：相对定位
    和绝对定位是根据具有定位属性的父元素来调整的，如果不存在定位属性则逐级向上直至顶端。）
## 7.圆角和阴影
    圆角border-radius。一个值：四个角（想设置成圆就输入50%或100%）；两个值：左上右下 右上左
    下；三个值：左上 右上左下 右下；四个值：左上 右上 右下 左下。
    阴影box-shadow。四个值分别代表水平阴影位置、垂直阴影位置、模糊距离和阴影颜色。
## 8.动画
    @keyframes name{from|0%{css}percent{css}to|100%{css}}。并在元素x标签里定义
    animation:name duration timing-function delay iteration-count direction。其中
    timing-function的值包括ease（默认 变慢）、linear（匀速）、ease-in（加速）、ease-out（减
    速）、ease-in-out（先加速后减速）；direction的值包括normal和alternate。设置好后添加
    x:hover{animation-play-state:paused;}
## 9.媒体查询
    媒体查询可以根据屏幕大小的不同显示相应内容。@media screen and (max-width:768px){x{}}
    @media screen and (min-width:768px) and (max-width:992px){x{}}@media screen and (min-width:992px){x{}}。
## 10.雪碧图
    通过background-image引入背景图片，再通过background-position调整位置。（注：如果使用内联
    元素时需要添加display:block）
## 11.字体图标
    优点：轻量级、灵活性、兼容性。推荐阿里字体图标库，添加并下载喜欢图标，然后在head例输入
    <link rel="stylesheet" href="./iconfont.css">。定义<span class="iconfont 
    icon-xxx"></span>。

