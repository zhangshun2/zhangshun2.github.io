# VUE指令
> 可以理解为vue视角的常用html属性 <br>
> @author zhangshun

---
> 属性是以v-开头的

## 常见vue的html标签属性整理

* v-html  :绑定的html标签
* v-bind  :绑定属性值
* v-bind:class  :绑定样式 , 举例v-bind:class="{'class1':data里的属性}"
* v-if  :是否生效
* v-bind:href  :绑定超链接
* v-on  :绑定dom事件 , 举例
    ~~~html
  <form v-on:submit.prevent="onSubmit"></form>
  ~~~
* v-model  :双向绑定

## 指令引申

* v-bind 缩写
> Vue.js 为两个最为常用的指令提供了特别的缩写：

~~~html
    <!-- 完整语法 -->
    <a v-bind:href="url"></a>
    <!-- 缩写 -->
    <a :href="url"></a>
~~~
    
* v-on 缩写

~~~html
    <!-- 完整语法 -->
    <a v-on:click="doSomething"></a>
    <!-- 缩写 -->
    <a @click="doSomething"></a>  
~~~  

## 实际例子参考连接
* [VUE基础语法和缩写等演示demo](https://www.runoob.com/vue2/vue-template-syntax.html)

## 自定义指令
* 语法块<br>

    Vue.directive(语法块名称,options)
    
* [超纲了,看了记不住,用的时候多回来翻翻载更新博客](https://www.runoob.com/vue2/vue-custom-directive.html)
