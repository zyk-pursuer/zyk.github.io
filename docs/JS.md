# JS学习教程
## 1.JS引入方式
    html引入（<Script></Script>）、本地独立JS文件引入（<script type="text/javascript" src="test.js"></script>和网络引入（<Script src="url"></Script>）。
## 2.注释与输出
    JS注释分为两种：单行注释（//）和多行注释（/*xxx*/）。
    HTML注释：<!--xxx-->
    CSS注释：/*xxx*/
    注释快捷键：ctrl+?
    JS常见输出方式：alert("要输出的内容")、document.write("要输出的内容")、
    console.log("要输入的内容")。
## 3.数据类型
    JS数据类型分为两类：基础类型和合成类型。基础类型包括数值、字符串（被单引号或双引号包裹）
    和布尔值；合成类型包括多个基础类型（用大括号来定义对象，基础类型之间用逗号隔开）。
    Undefined和null一般看成两个特殊值。
## 4.运算符
    typeof：检测变量的数据类型。可以使用console.log(typeof x)来打印x的数据类型。
    算术运算符：加（+）减（-）乘（*）除（/）取余（%）自增/自减（++x/--x）（x++/x--）（注：
    ++x和x++的区别在于前者先自增后运算，后者先运算后自增）。
    赋值运算符：等值（=）加等（+=）减等（-=）乘等（*=）除等（/=）取余等（%=）。
    比较运算符：返回布尔值。大于（>）小于（<）大于等于（>=）小于等于（<=）相等（==）
    严格相等（===）不相等（!=）不严格相等（!==）
    布尔运算符：
    取反（！）。非布尔值取反会转成布尔值，其中undefined、null、false、0、NaN和空字符串取反
    后的值为true，其他都是false。
    且运算符（&&）。多个条件同时满足。
    或运算符（||）。满足一个条件即可。
    条件运算符：if（布尔值）{执行A语句}else{执行B语句}（注：可以有多个else if，允许嵌套）。
    Switch（x）{case y：break；default}用于简化else if。（注：不加break会执行符合条件及其
    以后的结果）。
    三元运算符：（条件）？表达式1：表达式2。
## 5.循环语句
    for循环：for（初始表达式；布尔表达式；迭代因子）。三个都省略会死循环。
    while语句：while（条件）{语句；}
    break与continue：break跳出循环；continue跳出当前循环。
## 6.字符串
    字符串可以用单引号或者双引号引入，也可以互相嵌套，但是不允许单单嵌套或者双双嵌套。如果一定
    要的话，需要加上/作为转义符。同样，字符串默认一行，如果一定要换行的话也需要加转义符。
    str.charAt(x)返回第x位的字符。当x大于等于字符长度或者为复数时，返回空字符串。
    str.concat(x)将x与str相加。x可以有多个字符串，用逗号隔开。或者用+也可以相加。
    str.substring(x,y)返回第x位到第y-1位的字符串；如果省略y则到结束；如果x>y则自动调转x和y的
    位置；如果有负值则自动转换成0再调整相应位置。
    str.substr(x,y)返回从第x位起长度为y的字符串；如果省略y则到结束；如果x为负数则倒数开始；如
    果y为负数则返回空字符串。
    str.indexOf(x,y)表示从第y位起匹配x，有则返回位置，没有则返回-1；省略y则直接匹配。
    str.trim(x)删除x两边的空格、制表符(\t,\v)、换行符(\n)和回车符(\r)。ES6新增
    str.trimEnd(x)和str.trimStart(x)。
    str.split('x')将str以x方式切割；如果是空字符串则切割出每个字符；如果是空内容则返回整个字
    符串；字符串后可以添加第二个参数（以逗号隔开）用来限制切割最大个数。
## 7.数组
    数组里没有数据类型限制，允许先定义后赋值（赋值方式为str[x]，x为位置）。
    遍历数组有三种方式：
    for循环、while语句和for...in遍历（for(var i,in,str){console.log(str[i])}）。
    Array.isarray用于判断是不是数组，是则返回true，不是则返回false。
    push()可以在数组尾部添加一个或多个元素，并返回数组长度。
    pop()可以删除数组里的最后一个元素，并返回该元素。
    shift()可以删除数组里的第一个元素，并返回该元素。（可以用来清空数组，pop应该也可以）
    unshift()可以在数组头部添加一个或多个元素，并返回数组长度。
    join('x')将数组以x方式结合；如果是空内容则默认以逗号结合；如果数组元素有null或undefined
    或空位，则对应元素返回空字符串。join()和split()结合可以实现数组和字符串互相转换。
    concat()将一个或多个新数组（或其他类型数据）添加至原数组尾部。
    reverse()用于颠倒数组元素排列，可以用来生成倒序字符串。
    indexOf()与字符串中用法相同。
## 8.函数
    通过function name(){}来定义name函数，并在后续操作中调用该函数。
    对象里包括键值对（键名（属性）-键值），可以通过对象名.属性来调用对应键值。如果属性的数据类
    型为对象，则可以形成链式调用：对象名1.对象名2.属性。
    Math对象：Math.abs(), Math.max/min(), Math.floor/ceil()（向下/上取整）, 
    Math.random()（生成[0,1)之间的伪随机数）。
    Date对象获取日期信息（显示从1970年1月1日开始前后一亿天），分别以getMonth等获取。（注：
    获取四位数年份是getFullYear）。new Date获取当前日期。getTime获取从1970年开始的毫秒数。
## 9.DOM
    DOM是js操作网页的接口，全称是文档对象模型。它的作用是将静态网页转换成js脚本，方便删减元
    素。
    DOM的最小单位是节点。节点一共有七种类型：Document（顶层节点）, DocumentType（doctype
    标签）, Element（html标签）, Attribute（元素属性）, Text（文本）, Comment（注释）, 
    DocumentFragment（文档片段）。
    不同节点的nodeType属性值和对应的常量如下：文档9、元素1、属性（attr）2、文本3、文档片段11。
### 9.1 Document获取元素
|对象名|描述|
|:---:|:---:|
|document.GetElementsByTagName|通过标签名获取元素|
|document.GetElementsByClassName|通过类名获取元素动态集合|
|document.GetElementsByName|用于有name属性的元素|
|document.GetElementById|通过ID获取元素（不常用）|
|document.QuerySelector|接受CSS选择器作为参数，返回第一个|
|document.QuertSelectorAll|返回所有静态节点结合|
### 9.2 Document创建元素
|对象名|描述|
|:---:|:---:|
|document.createElement|生成元素节点并返回该节点|
|document.createTextNode|生成文本节点并返回该节点|
|document.createAttribute|生成新的属性节点|
### 9.3 Element属性
|对象名|描述|
|:---:|:---:|
|Element.id|返回指定对象的id（支持读写）|
|Element.className|返回指定对象的class（支持读写，不同class以空格隔开）|
|Element.classList|.add()增加.remove()移除.contain()检查存在.toggle()移入移出|
|Element.innerHTML|返回元素包含的所有HTML代码（支持读写）|
|Element.innerText|类似innerHTML，但是无法识别元素，会直接渲染成字符串|
### 9.4 Element获取元素位置
|对象名|描述|
|:---:|:---:|
|clientHeight|获取元素高度（包括padding，不包括border和margin）|
|clientWidth|获取元素宽度（包括padding，不包括border和margin）|
|scrollHeight|元素总高度（包括padding，不包括border和margin）|
|scrollWidth|元素总宽度（包括padding，不包括border和margin）|
|scrollLeft|元素水平滚动条向右滚动的像素数量|
|scrollTop|元素水平滚动条向下滚动的像素数量|
|offsetHeight|元素的CSS垂直高度（包括padding，border和margin）|
|offsetWidth|元素的CSS水平宽度（包括padding，border和margin）|
|offsetLeft|到定位父级左边界的间距|
|offsetTop|到定位父级上边界的间距|
注：clientHeight在document.documentElement是当前窗口高度，而在document.body是实际高度。
### 9.5 CSS操作
    直接操作setAttribute、操作元素节点的style属性.style.属性名以及cssText属性.style.cssText。
## 10.事件
    事件分为HTML事件、DOM0级事件和DOM2级事件。
    HTML事件
    ```js
    <button onclick="clickHandle()">按钮</button>
    <script>
        function clickHandle(){
            console.log("点击了按钮");
        }
        // 缺点：HTML和JS没有分开
    </script>
    ```
    DOM0事件
    <button id="btn">按钮</button>
    <script>
        var btn = document.getElementById("btn")
        btn.omclick = function(){
            console.log("点击了按钮");
        }
        // 优点：HTML和JS分开   缺点：无法同时添加多个事件
    </script>
    DOM2事件
    <button id="btn">按钮</button>
    <script>
        var btn = document.getElementById("btn")
        btn.addEventListener("click",function(){
            console.log("点击了按钮");
        })
        // 优点：可以同时添加多个事件   缺点：写起来麻烦
    </script>
### 10.1 鼠标事件
|事件名|描述|
|:---:|:---:|
|click|按下鼠标时触发|
|dblclick|在同一个元素上双击鼠标时触发|
|mousedown|按下鼠标键时触发|
|mouseup|释放鼠标键时触发|
|mousemove|鼠标移动时触发|
|mouseenter|鼠标进入节点时触发（不包括子节点）|
|mouseleave|鼠标离开节点时触发（不包括父节点）|
|mouseover|鼠标进入节点时触发（包括子节点）|
|mouseout|鼠标离开节点时触发（包括父节点）|
|wheel|滚动滚轮时触发|
### 10.2 Event事件对象
    常见Event对象属性包括Event.target和Event.type。Event.target返回事件当前所在节点；
    Event.type返回事件类型。
    常见Event对象方法包括Event.preventDefault()和Event.stopPropagation()。
    Event.preventDefault()阻止默认事件的发生；
    Event.stopPropagation()阻止事件在DOM中继续传播，防止再触发定义在别的节点上的监听函数。
### 10.3 键盘事件
|事件名|描述|
|:---:|:---:|
|keydown|按下键时触发|
|keypress|按下有值的键触发|
|keyup|松开键时触发|
    event对象keyCode：唯一标识
### 10.4 表单事件
    表单事件是在使用表单元素及输入框元素时可以监听的一系列事件。
    input事件在值发生变化时触发，可以连续触发。
    select事件在选中文本时触发。
    change事件类似input，区别在于不会连续触发，只有在全部修改完时触发。
    reset事件发生在表单对象<form>上，当所有成员重置时触发。
    submit事件发生在表单对象<form>上，提交表单数据时触发。
### 10.5 事件代理
    将子节点的监听函数定义在父节点上，由父节点来统一处理多个子元素事件的方法叫做事件代理。
## 11.定时器
    setTimeout(function|code,x)设定函数或代码在x毫秒后执行。clearTimeout可以取消定时器。
    setInterval和setTimeout用法一致，区别在于setInterval每隔一段时间执行。
## 12.防抖
    防抖目的是优化性能，通过设定某一操作在一定时间内只执行一次来实现。
    ```js
    <script>
        function debounce(fn,delay){
            var timer = null;
            return function(){
                if(timer){
                    clearTimeout(timer)
                }
                timer = setTimeout(fn,delay)
            }
        }

        window.onscroll = debounce(scrollHandle,200)

        function scrollHandle(){
            var scrollTop = document.documentElement.scrollTop;
            console.log(scrollTop);
        }
    </script>
## 13.节流
    节流的目的也是优化性能，通过让函数在一定时间内执行一次后失效来实现。
    <script>
        function throttle(fn,delay){
            var valid = true;
            return function(){
                if(!valid){
                    return false;
                }
                valid = false;
                setTimeout(function(){
                    fn();
                    valid = true;
                },delay)
            }
        }

        window.onscroll = throttle(scrollHandle,200)

        function scrollHandle(){
            var scrollTop = document.documentElement.scrollTop;
            console.log(scrollTop);
        }
    </script>


