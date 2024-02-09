# Vue学习教程
## 1.开发准备
    Vue CLI是一个基于Vue.js进行快速开发的完整系统
    步骤：
    1.通过npm进行安装：npm install -g @vue/cli。安装完后通过vue --version来验证是否安装成功。
    2.安装成功后输入vue create vue-demo来新建一个文件夹(注意：如果报错可能是powershell默认禁止
    vue，以管理员身份运行powershell然后输入set-ExecutionPolicy RemoteSigned，弹出对话后输入y即
    可。)
    3.进入选择界面后分别选择Manually select features、Babel，PWA（注意取消勾选倒数第三个）、3.x、
    In dedicated config files、No即可完成配置。
    4.进入vue-demo文件夹输入npm run serve即可通过本地或者IP访问界面。
    注意：可以选择安装vue高亮插件vetur（vue2）或者volar（vue3）。
## 2.具体教程
详见[官方文档](https://cn.vuejs.org/guide/introduction.html)。