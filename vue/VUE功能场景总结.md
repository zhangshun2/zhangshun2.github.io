# vue功能场景

## 判断

* v-if 配合 v-else
* v-if 配合 v-else-if 和v-else 
* v-show 判断是否显示

### 举例

~~~html
<div id="app">
    <div v-if="type === 'A'">
      A
    </div>
    <div v-else-if="type === 'B'">
      B
    </div>
    <div v-else-if="type === 'C'">
      C
    </div>
    <div v-else>
      Not A/B/C
    </div>
</div>
<h1 v-show="ok">Hello!</h1>
<script>
new Vue({
  el: '#app',
  data: {
    type: 'C'
  }
})
</script>
~~~

## 循环
* v-for="元素 in 集合"   {{ 元素.属性 }}
~~~html
<div id = 'app-5'>
    <li v-for="demo in demos">
        {{ demo.name }}
    </li>
</div>
<script>
    new Vue({
        el: '#app-5',
        data: {
            demos:[{name:'zhangshun'},{name:'wutao'}]
        }
    })
</script>
~~~

