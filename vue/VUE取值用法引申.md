# VUE取值用法引申
> @author zhangshun

---
## 用法引申filter
vue对象里的属性有一个filter , 可以理解为特殊的methods
则引申: 在{{}}中取值时支持如下操作
    

    {{ 值 | 过滤器(一般是filter里的一个函数) }}
    // 过滤器可以串联
    {{ 值 | 过滤器(一般是filter里的一个函数) | 过滤器(一般是filter里的一个函数) }}
    
## 用法引申computeds
* 类似methods ,但是区别是computeds会依赖缓存
* 且computeds内可以写属性,且树形默认提供getter方法,setter方法需要手动创建,具体用法参照java
~~~js
var vm = new Vue({
  el: '#app',
  data: {
    name: 'Google',
    url: 'http://www.google.com'
  },
  computed: {
    site: {
      // getter
      get: function () {
        return this.name + ' ' + this.url
      },
      // setter
      set: function (newValue) {
        var names = newValue.split(' ')
        this.name = names[0]
        this.url = names[names.length - 1]
      }
    }
  }
})
// 调用 setter， vm.name 和 vm.url 也会被对应更新
vm.site = '菜鸟教程 http://www.runoob.com';
document.write('name: ' + vm.name);
document.write('<br>');
document.write('url: ' + vm.url);
~~~

## 用法引申watch
* 类比于methods
* 写data中属性相关的函数.被v-model双向绑定的会直接触发.
举例
~~~html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>Vue 测试实例 - 菜鸟教程(runoob.com)</title>
	<script src="https://cdn.staticfile.org/vue/2.4.2/vue.min.js"></script>
</head>
   <body>
      <div id = "computed_props">
         千米 : <input type = "text" v-model = "kilometers">
         米 : <input type = "text" v-model = "meters">
      </div>
	   <p id="info"></p>
      <script type = "text/javascript">
         var vm = new Vue({
            el: '#computed_props',
            data: {
               kilometers : 0,
               meters:0
            },
            methods: {
            },
            computed :{
            },
            watch : {
               kilometers:function(val) {
                  this.kilometers = val;
                  this.meters = this.kilometers * 1000
               },
               meters : function (val) {
                  this.kilometers = val/ 1000;
                  this.meters = val;
               }
            }
         });
         // $watch 是一个实例方法
		vm.$watch('kilometers', function (newValue, oldValue) {
			// 这个回调将在 vm.kilometers 改变后调用
		    document.getElementById ("info").innerHTML = "修改前值为: " + oldValue + "，修改后值为: " + newValue;
		})
      </script>
   </body>
</html>
~~~

## 样式绑定v-bind:class 或者 :class
* value的范围: key是css样式的名称 , value是data中值的范围<br>
举例

~~~html
<!DOCTYPE html>
       <html>
       <head>
       <meta charset="utf-8">
       <title>Vue 测试实例 - 菜鸟教程(runoob.com)</title>
       <script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
       <style>
       .active {
       	width: 100px;
       	height: 100px;
       	background: green;
       }
       .text-danger {
       	background: red;
       }
       </style>
       </head>
       <body>
       <div id="app">
         <div class="static"
            v-bind:class="{ 'active': isActive, 'text-danger': hasError }">
         </div>
       </div>
       
       <script>
       new Vue({
         el: '#app',
         data: {
           isActive: true,
       	hasError: true
         }
       })
       </script>
       </body>
       </html>
~~~

或者 直接使用对象data

~~~html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Vue 测试实例 - 菜鸟教程(runoob.com)</title>
<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
<style>
.active {
	width: 100px;
	height: 100px;
	background: green;
}
.text-danger {
	background: red;
}
</style>
</head>
<body>
<div id="app">
  <div v-bind:class="classObject"></div>
</div>

<script>
new Vue({
  el: '#app',
  data: {
    classObject: {
      active: true,
      'text-danger': true
    }
  }
})
</script>
</body>
</html>
~~~

或者使用内联样式 , 直接bind:stype,但是值从data中取

~~~html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Vue 测试实例 - 菜鸟教程(runoob.com)</title>
<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
</head>
<body>
<div id="app">
	<div v-bind:style="{ color: activeColor, fontSize: fontSize + 'px' }">菜鸟教程</div>
</div>

<script>
new Vue({
  el: '#app',
  data: {
    activeColor: 'green',
	fontSize: 30
  }
})
</script>
</body>
</html>
~~~

## vue事件处理
* 配合函数触发就好
[常见例子参考](https://www.runoob.com/vue2/vue-events.html)

## v-model引申
*   v-model.trim 去空格
*   补充type='number'自动转数字
*   v-model.lazy 会自动同步change事件


