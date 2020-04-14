## 一、什么是前端？前端都包括哪些内容

#### 1. 前端历史 

2014之前：HTML，CSS，JavaScript，jQuery（2006，JavaScript函数库），Bootstrap(UI)

2014年—2016年：NodeJS，Angular（谷歌），React（Facebook），Vue（华人，尤雨溪）

2017年之后：小程序等等

#### 2.前端代码体验

使用HTMl构建页面结构

使用CSS修饰页面的效果

使用JavaScript实现动态效果：

2.1 获取HTML元素

2.2 添加事件改变元素内容或样式

#### 3. VSCode前端环境配置

3.1 安装Beautify，它用来格式化代码

3.2 安装open in browser  右键选中可以直接在浏览器中查看页面效果

3.3 HTML Snippets 代码自动填充

3.4 Vetur  支持Vue 

3.5 Live server 浏览器实时更新

3.6 Vue 2 Snippets  vue代码提示

## 二、动手写一个购物车效果

#### 1. HTML，CSS，JavaScript，jQuery，Bootstrap

引入库：https://www.bootcdn.cn/

#### 2. 非工程化方式的Vue

v-model 双向数据绑定

v-for 循环遍历，渲染列表项

v-bind 绑定数据和元素属性

v-on  事件绑定

## 三、动手写一个TODOList应用

设置一个倒计时，比如说初始时间是25分钟，进入work（工作）状态，25分钟到点后就是一个5分钟的rest（休息）状态，如此反复



## 四、Vue2.X工程化环境搭建

1. 下载nodejs：https://nodejs.org/en/，npm包管理工具

   检查是否已经安装，cmd中输入node -v检查node ，npm -v 检查npm

2. 用管理员身份打开cmd或者cmder或者gitbash：运行npm install -g vue-cli，vue-cli是vue的脚手架工具  ，Mac Terminal中增强权限sudo

   如果之前安装过，可以先卸载 vue-cli：npm uninstall -g vue-cli

   输入vue --version检查是否安装成功

3. 初始化项目  vue init webpack practise

   进入到项目中  cd practise

   运行项目  npm run dev

4. 启动单元测试：npm run unit

5. 启动端对端测试e2e：npm run e2e，因为selenium需要Java的环境，所以先要安装Java的JDK（关注右侧公众号，点击java即可获取安装视频），安装好之后，先把谷歌浏览器升级到最新版本，然后把node_modules中的chrome-driver文件夹删掉，把package.json中的chrome-driver依赖删掉，执行一下npm install；最后执行 npm install chromedriver --chromedriver_cdnurl=https://npm.taobao.org/mirrors/chromedriver  从淘宝的镜像安装chrome-driver即可。（关键点：chrome一定要是最新，chrome-driver也是最新，这两个版本一定一定要对应，否则会报错，谷歌设置成默认浏览器）

6. 安装vue-devtools，打开 https://github.com/vuejs/vue-devtools ，将Branch切换到master分支，再点击clone or download按钮下载；下载完成后，将压缩包解压，进入到vue-devtools文件夹中，执npm install (安装依赖)，运行完成后，再执行npm run build (编译文件)。打开谷歌浏览器的设置—> 扩展程序—>加载已解压的扩展程序（确保右上角开发者模式已经打开），选中vue-devtools文件夹中的shells中的chrome文件夹即可，重启浏览器生效。

## 五、MVVM架构

MTV，MVC

1. 名词解释  View（div #app）         Model（var data）       ViewModel

   Model-View-ViewModel     MVVM

2. 数据传入Vue实例后发生了什么？

   ```
   var obj = {}
   undefined
   var text = ''
   undefined
   var oH2 = document.getElementsByTagName('h2')[0]
   undefined
   Object.defineProperty(obj,'text',{
     get:function(){ return text; },
     set:function(newVal){text=newVal;oH2.innerHTMl=text;}
   });
   {}text: (...)get text: ƒ ()set text: ƒ (newVal)__proto__: Object
   obj.text = "nidedingdan"
   "nidedingdan
   ```

   通过setters，getters方法实现的双向数据绑定，数据驱动



## 六、Vue.js基础

1. 组件（灵活，可复用，每个组件都有属于自己的样式和模板，完全独立的）

   创建组件： var ItemsComponents = Vue.extend({ })

   注册组件：Vue.component('items-component',ItemsComponents)

   使用组件：<'items-component></'items-component>

   购物车案例可以拆分为：添加到购物车，列表，改变标题

2. 指令(自定义指令)

   注册自定义指令，用到三个函数：

   bind：向元素附加一个事件监听器，

   update：接收新值和旧值作为参数（数据变化时自定义行为）

   unbind：解绑所有需要解除的操作

3. 插件

   插件是Vue的核心功能，它提供了对数据绑定的声明及组件编译。

   插件的主要分类：

   - 增加全局的属性或者方法(vue-element)
   - 增加全局能力的插件(vue-touch)
   - 在Vue属性上增加Vue实例
   - 提供一些扩展功能或API（vue-router）

   插件的用法：必须通过一个可以增强或改进的全局的Vue对象来提供一个实例方法。Vue使用use方法来接收插件实例 Vue.use()

4. 从package.json构建Vue工程

   npm install -g browserify  安装browserify

   ```json
   "devDependencies": {
           "babel-preset-es2015": "^6.24.1", //将ES6语法转换成浏览器可以使用的ES5的语法
           "babelify": "^7.3.0",  //必须是这个7.x版本
           "browserify": "^16.5.1",//JavaScript构建工具，和webpack类似 
           "vue": "^2.6.11"
    },
   ```

   browserify script.js -o main.js -t [ babelify --presets [ es2015 ] ]

   

5. Vuex状态管理器

   安装vuex   ： npm install vuex 

   ```
   /script.js
   
   import Vuex from 'vuex'
   Vue.use(Vuex)
   var store = new Vuex.Store({
       state:{message: 'Hello!'},
       mutations:{}
   })
   
   
   new Vue({
       el:'#app',
       data:{
           item:20
       },
       store:store
   })
   ```

   

6. vue init      vue init webpack    vue init  browserify    的目录结构区别

   项目构建工具，用来打包资源的：img，html，css，JavaScript。。。

   webpack：全部的资源都能打包

   browserify：只能打包JavaScript资源

7. 桌面新建一个simple文件夹，cd simple

   vue init simple  一直回车   只生成了一个引入了vue.js的index.html文件

   vue init webpack webpack-simple

   vue init browserify browserify-simple   

   观察以上命令行生成的目录结构

   















































































