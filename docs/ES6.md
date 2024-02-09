# ES6学习教程
## 1.命令行工具
    清空命令行信息：cls
    快速补全目录或文件夹名称：tab
    查看历史输入过的命令：上下按键
## 2.Nodejs
    主要内容集中在npm上，可以通过阿里云镜像http://npmmirror.com访问。
## 3.let命令和const命令
    let命令和var有点相似，区别在于let是块级作用域，var是函数级作用域。let不存在变量提升，不允许
    重复声明。
    const命令用于声明常量，需要立刻赋值，不允许改变值，不存在变量提升，属于块级作用域，不允许重复
    声明。
## 4.对象解构赋值
    解构可以用于对象，对象的属性没有次序。对象解构赋值可以很方便地将现有对象方法赋值到某个变量。
## 5.字符串扩展
    - 支持Unicode；
    - 支持遍历for...of...
        for(let i of 'x'){
            console.log(i);
        }
    - 模板字符串
        let x =`<a href='${url}'>${xxx}</a>`
## 6.字符串新增方法
    JS中只有indexOf用来判断一个字符串是否包含在另一字符串中，ES6新增了includes|startsWith|endsWith。
    这三种方法都支持添加第二个参数，表示开始搜索的位置。
    repeat(x)表示将源字符串重复x次。
    padStart(x,'y')表示从源字符串的第x位起填充字符串y；padEnd同理。
    trimStart删除源字符串的头部空格；trimEnd删除尾部。
    at返回指定位置的参数。
## 7.数组扩展
    ...可以将数组每个元素提取出来并转换成元素序列。
## 8.数组新增方法
    类数组（伪数组）可以使用数组的读取方式和length，但不能使用数组方法。
    常见的类数组（伪数组）有三类：arguments、元素集合和类似数组的对象。
    Array.from可以将类数组转换成数组；Array.of可以将一组值转换成数组。
## 9.对象扩展
    ES6允许在对象的大括号里直接写入变量和函数，也可以简写方法。
    JS定义对象的属性有两种：标识符（obj.foo = true）和表达式obj['a'+'bc']=123。如果使用字面量方式
    定义对象（即用大括号），在ES5中只能使用标识符，而ES6可以使用表达式，即把表达式放在方框里。
    ...也可以用于对象。
## 10.函数扩展
    ES6允许使用箭头=>来定义函数：var add = (x,y) => x+y。（一个参数不需要括号，其他都要）
    如果箭头函数的代码块部分多余一条语句，就要用大括号把它们括起来，并且使用return语句返回。
    var add = (x,y) => {
        var z = 10;
        return x+y+z
    }
    由于大括号被解释为代码块，所以如果返回一个对象的话，需要在对象外面加上括号，否则会报错。
    var add = (x,y) => ({x:10,y:20})
    箭头函数可以简化回调函数（匿名函数）
    var arr = [10,20,30]
    arr.map(item =>{
        console.log(item);
    })
    普通函数内部的this指向函数运行时所在的对象，但是箭头函数内部的this就是定义时上层作用域的this。
## 11.set数据结构
    ES6提供了新的数据结构Set。它类似于数组，但是成员的值不重复。
    Set函数可以接受数组作为参数，可用于去除重复成员。
    Set也可以使用扩展运算符来读取数据。
    向Set加入值的时候，不会发生类型转换。
    size属性用于返回Set的成员总数。
    Set常用方法：
|方法|描述|
|:---:|:---:|
|add()|向Set里添加成员|
|delete()|删除Set里某一成员|
|has()|返回一个布尔值，表示是否包含某个值|
|clear()|清除所有成员，没有返回值|
## 12.Promise对象
    Promise是异步编程的一种解决方案，从语法上说是对象。
    Promise提供统一的API，各种异步操作都可以用同样的方法进行处理。
    const promise = new Promise(function(resolve, reject){
        //可以添加自己想展示的内容
        if(/* 异步操作成功 */){
            resolve(value);
        } else {
            reject(error);
        }
    });
    在生成Promise实例后，可以用then方法分别指定resolved状态和rejected状态的回调函数。
    promise.then(function(value){
        // success
    }, function(error){
        // failure
    });
## 13.async函数
    async函数可以将异步操作变为同步操作。
    在需要执行的函数前添加async，再在里面具有异步属性的函数前添加await即可。
## 14.class
    ES6引入了类作为对象的模板，让写法更加清晰。
    class Person {
        constructor(name){
            this.name = name;
        }
    }

    var p = new Person("123")
    constructor是类的默认方法，通过new命令生成对象实例时自动调用，没有定义时会默认添加空方法。
    注意：类不存在变量提升。
### 14.1 class属性
    实例属性：类的实例对象可调用的属性。
    静态属性：class本身的属性。
### 14.2 class方法
    实例方法：通过类的实例对象调用方法。
    静态方法：所有在类中定义的方法都会被实例继承，如果在一个方法前加上static关键字就表示该方法
    不会被实例继承，而是直接通过类来调用，这就是静态方法。
    class Person {
        static classMethod(){
            console.log("Hello");
        }
    }
     Person.classMethod() //Hello

     var p = new Person();
     p.classMethod() //p.classMethod is not a function.
     注意：如果静态方法中包含this，那么this指的是类而不是实例。
## 15.Module
    传统JS在不同js文件里声明变量后会相互引用，这样在开发大型项目时一旦所声明的变量重名就会报错。因此
    ES6引入了Module使得不同js的变量可以保持独立。
    实现原理：在js文件A中需要输出的变量前添加export，在js文件B中添加import {} from "./A.js"。（注
    意：export既可以导出变量，也可以导出函数。）
    如果想为引入的变量重新取一个名字，import命令可使用as来重命名。
    如果想全部引入，可以使用* as x，然后用x来调用所有内容。
    export default可以为模块制定默认输出，这样其他模块调用时import可以为该匿名函数制定任意名字。
    （注意：一个模块里只允许出现一个export default）
    可以使用Nodejs测试Module语法。（注意：Nodejs采用的是CommonJS的模块化规范，使用require引入模
    块；而import是ES6的模块化规范关键字。想要使用import，必须引入babel转义支持，通过babel进行编
    译，使其变成node的模块化代码。）
    步骤：
    1.全局安装babel-cli                     npm install -g babel-cli
    2.在需要目录下安装babel-preset-env       npm install -D babel-preset-env
    3.运行代码                              babel-node --presets env index.js