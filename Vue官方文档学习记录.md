# 什么是Vue

Vue (读音 /vjuː/，类似于 **view**) 是一套用于构建用户界面的**渐进式框架**。与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与[现代化的工具链](https://cn.vuejs.org/v2/guide/single-file-components.html)以及各种[支持类库](https://github.com/vuejs/awesome-vue#libraries--plugins)结合使用时，Vue 也完全能够为复杂的单页应用提供驱动。

优点：

vue是一套构建用户界面的框架，只关注视图层，所以易上手，而且也便于与第三方库或既有项目整合。（vue的优点）





# 库与框架的区别

框架：一套完整的解决方案，对项目侵入性比较大，与项目耦合度高

库：提供一个小的功能，更换库的代价小。耦合度小











# 起步

## 声明式渲染：

插值：

```html
<div>
{{message}}
</div>
```



元素attribute 绑定：v-bind:

```html
<span v-bind:title="message">
	
</span>
```

title属性attribute与message property保持一致





## 条件与循环渲染

条件：v-if

```vue
<p v-if="seen">
可以看到
<p>
```



循环：v-for

```Vue
	<li v-for="todo in todos">
	{{todo.text}}
	</li>
```





## 处理用户输入

v-on事件监听：

```
<div>
<button v-on:click="函数名">
	按钮
</button>
</div>
```

**函数**在Vue实例中定义



双向绑定：v-model

用于实现表单输入与应用状态之间的双向绑定

```Vue
<input v-model="message">
```



## 组件

Vue中的组件本质上是一个拥有预定义选项的一个Vue实例

在Vue中注册组件：

```
Vue.component('todo-item',
{
	template:'<li>这是个待办项<li>'
}
)
```

<todo-item></todo-item>





## Vue实例：

```js
let vm=new Vue({
//选项
})
```





## 生命周期钩子

create：



```js
new Vue({
  data: {
    a: 1
  },
  created: function () {
    // `this` 指向 vm 实例
    console.log('a is: ' + this.a)
  }
})
// => "a is: 1"
```

先罗列出生命周期然后一个一个讲解

beforeCreate

created

beforeMount

mounted

beforeUpdate

updated

beforeDestroy

destroyed



beforeCreate：

实例组件刚创建，元素DOM和数据都还没有初始化，暂时不知道能在这个周期里面进行生命操作。

created

数据data已经初始化完成，方法也已经可以调用，但是DOM未渲染。有人问了，请求都是异步的，并不会阻碍实例加载。这是我个人水平的问题，这边改正，在这个周期里面，请求因为是异步的，不会阻碍实例加载，除非是那些同步操走才会导致页面空白。这样说来，在这个周期里面进行请求，渲染速度反而会更快。

beforeMount

DOM未完成挂载，数据也初始化完成，但是数据的双向绑定还是显示{{}}，这是因为Vue采用了Virtual DOM（虚拟Dom）技术。先占住了一个坑。

mounted

数据和DOM都完成挂载，在上一个周期占位的数据把值给渲染进去。可以在这边请求，不过created请求会更好一些。这个周期适合执行初始化需要操作DOM的方法。

beforeUpdate

只要是页面数据改变了都会触发，数据更新之前，页面数据还是原来的数据，当你请求赋值一个数据的时候会执行这个周期，如果没有数据改变不执行。

updated

只要是页面数据改变了都会触发，数据更新完毕，页面的数据是更新完成的。beforeUpdate和updated要谨慎使用，因为页面更新数据的时候都会触发，在这里操作数据很影响性能和容易死循环。

beforeDestroy

这个周期是在组件销毁之前执行，在我项目开发中，觉得这个其实有点类似路由钩子beforeRouterLeave,都是在路由离开的时候执行，只不过beforeDestroy无法阻止路由跳转，但是可以做一些路由离开的时候操作，因为这个周期里面还可以使用data和method。比如一个倒计时组件，如果在路由跳转的时候没有清除，这个定时器还是在的，这时候就可以在这个里面清除计时器。

Destroyed

说实在的，我还真的不知道这个周期跟beforeDestroy有什么区别，我在这个周期里面调用data的数据和methods的方法都能调用，所以我会觉得跟beforeDestroy是一样的。



作者：wade3po
链接：https://www.jianshu.com/p/5cd198945d41
来源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。







## 模板语法

文本：

```
{{双大括号}}
```

来文本差值

v-once指令 来执行一次性插值  也就是一次改变后不会再对绑定的数据变动做出反应





原始html：

v-html命令：

```js
<p v-html='rawHtml'></p>
```

rawHtml中的字符串就是html的具体代码直接作为html

**绝不要**对用户提供的内容使用插值。



## arrtibute

因为双括号语法不能用到attribute上，应该用到v-bind指令

```js
<div v-bind:id="dynamicId"></div>
```



## 使用js的表达式

注意到这是表达式

```js
{{ number + 1 }}

{{ ok ? 'YES' : 'NO' }}

{{ message.split('').reverse().join('') }}

<div v-bind:id="'list-' + id"></div>
```



在遇到语句及控制流的时候不会生效

```js
<!-- 这是语句，不是表达式 -->
{{ var a = 1 }}

<!-- 流控制也不会生效，请使用三元表达式 -->
{{ if (ok) { return message } }}
```

## 指令

带有v-前缀的attribute   值得预期的单个的js表达式

指令职责是当表达式的值改变时 将其产生的连带影响，响应式地作用于DOM树



### 参数

指令接收的参数一般在指令之后用冒号：来表示

```js
<a v-bind:href="url"> </a>
```

在这里  href就是参数，v-bind就是把这里的href与url的值进行绑定

```js
<a v-on:click="doSomething">...</a>
```

这里v-on指令 接受的attribute参数就是click

### 修饰符

用以指出该指令用特殊的方式绑定

例如，`.prevent` 修饰符告诉 `v-on` 指令对于触发的事件调用 `event.preventDefault()`：

```js
<form v-on:submit.prevent="onSubmit">...</form>
```



### 缩写：

v-bind缩写：用冒号：

```js
<!-- 完整语法 -->
<a v-bind:href="url">...</a>

<!-- 缩写 -->
<a :href="url">...</a>

<!-- 动态参数的缩写 (2.6.0+) -->
<a :[key]="url"> ... </a>
```

v-on缩写：用@

```js
<!-- 完整语法 -->
<a v-on:click="doSomething">...</a>

<!-- 缩写 -->
<a @click="doSomething">...</a>

<!-- 动态参数的缩写 (2.6.0+) -->
<a @[event]="doSomething"> ... </a>
```



## 计算属性与方法的比较

计算属性：

```js
 computed: {
    // 计算属性的 getter
    reversedMessage: function () {
      // `this` 指向 vm 实例
      return this.message.split('').reverse().join('')
    }
  }
```

方法：

```js
methods: {
  reversedMessage: function () {
    return this.message.split('').reverse().join('')
  }
}
```

​	只在相关响应式依赖发生改变时它们才会重新求值。这就意味着只要 `message` 还没有发生改变，多次访问 `reversedMessage` 计算属性会立即返回之前的计算结果，而不必再次执行函数。