# VUE基本语法糖
> @author zhangshun
---

## 作用域
* 作用于
~~~html
<div id = 'element的id,这里在vue的视角理解为绑定标识 后面简称为BS'> <div>
~~~
* BS可以跟vue对象做绑定
    * vue对象基本语法
~~~js
var 变量名 = new Vue({
    el:'#BS', // #加上BS
    data: XXX , // 是个json结构 , 指明了BS内可以直接使用的变量
                // json结构中属性值可以是直观的值,也可以是html代码
    methods: {
        函数名: function(参数名0-n个) {
          return 返回值; // 可以操作data里的值
        }
    }
 })  
~~~
* {{ }} 用于输出对象属性和函数返回值 比如
~~~html
<div id="vue_det">
    <h1>site : {{site}}</h1>
    <h1>url : {{url}}</h1>
    <h1>{{details()}}</h1>
</div>
~~~  
* 变量名.$data里的值可以直接当做一个var去做操作.
* 如果data是外部传入的,则外部data变更,则内部data也变更

更详细的内容参考 [vue | 菜鸟教程](https://www.runoob.com/vue2/vue-start.html)