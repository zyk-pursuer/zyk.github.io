# Markdown进阶
## 1.如何使用md调整列表宽度
方法1：使用&nbsp或&emsp（等于四个&nbsp）填充。效果如下：
|名字&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|地址&emsp;&emsp;&emsp;|
|:---:|:---:|
|张三|浙江|
注：可以在最后一行增加空白行，然后填充最后一行即可。

方法2：使用空标签。效果如下：
|名字<img width=400/>||地址<img width=400/>|
|:---:|:---:|
|张三|浙江|

方案3：使用div标签。效果如下：
|<div style="width:400">名字</div>||地址|
|:---:|:---:|
|张三|浙江|
