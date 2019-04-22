## Vue.js学习记录

官网文档：https://cn.vuejs.org

### step-1：hello Vue

参考官网文档[介绍](https://cn.vuejs.org/v2/guide/index.html)这一节，初步了解vue的基本语法等内容。

### step-2：TodoList

通过实现一个todolist进一步来熟悉vue中的`v-if`、`v-for`、`v-bind`、`v-on`、`v-model`、计算属性等概念。

todolist的基本功能有：通过表单输入添加待办事项，删除已完成事项，筛选事项列表。

### step-3：Component

参考官方文档[组件基础](https://cn.vuejs.org/v2/guide/components.html)，学习组件相关内容。

#### 组件是可复用的Vue实例。

#### 一个组件的`data`必须是一个函数，而不是一个对象。

正因为如此，每个实例才可以维护一份被返回对象的独立的拷贝，也就是说，多次复用的组件之间不会相互影响。

#### 组件注册

1）全局注册

全局注册的组件可以用在任何新创建的Vue跟实例（`new Vue`）的模板中。

```
Vue.component('component-a', { /* ... */ })
Vue.component('component-b', { /* ... */ })
Vue.component('component-c', { /* ... */ })

new Vue({ el: '#app })

<div id="app>
    <component-a></component-a>
    <component-b></component-b>
    <component-c></component-c>
</div>
```

上面创建的三个组件在各自内部也都是可以相互使用的。

2）局部注册

通过一个普通的JavaScript对象来定义组件，然后在`components`选项中定义要使用的组件。

```
var ComponentA = { /* ... */ }
var ComponentB = { /* ... */ }
var ComponentC = { /* ... */ }

new Vue({
    el: '#app',
    components: {
        // 属性名为自定义元素的名字，属性值为这个组件的选项对象
        'component-a': ComponentA,
        'component-b': ComponentB
    }
})
```

局部注册的组件在其子组件中不可用。
如果想要`ComponentA`在`ComponentB`中可用：

```
var ComponentA = { /* ... */ }
var ComponentA = {
    components: {
        'component-a': ComponentA
    }
}
```

#### Prop

Prop是你可以在组件上注册的一些自定义特性。当一个值传递给一个prop特性时，它就变成了那个组件实例的一个属性。
数据流是单向的。父组件可以通过Prop向子组件传递数据，但是反过来不行。

### step-4：Vue Router

官网文档：https://router.vuejs.org/zh/

### step-5：Vuex

官方文档：https://vuex.vuejs.org/zh/

Vuex是一个专为Vue.js应用程序开发的状态管理模式。

几个核心概念：

- State
- Getter
- Mutation
- Action
