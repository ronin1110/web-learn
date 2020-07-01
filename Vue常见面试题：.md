# Vue常见面试题：

# 什么是vue的生命周期：

Vue实例从创建到销毁的全过程，就是生命周期，也就是从开始创建，初始化数据，编译模板，挂载DOM->渲染，更新->渲染，卸载等一系列过程，我们称之为vue的生命周期。



# vue的生命周期的作用是什么

生命周期中又很多的事件钩子，让我们在vue实例的过程时更容易形成好的逻辑。

# vue的生命周期共有几个阶段

一共有8个阶段：

创建前后

载入前后

更新前后

销毁前后



# 第一次页面会触发几个钩子

第一次页面加载会触发

beforeCreate

created

beforeMount

Mounted



# dom渲染在哪个周期内完成

DOM渲染在mounted





# 生命周期的一些钩子的用法

1. beforeCreate：可以在加载实例的时候触发

2. created：初始化完成时的事件卸载这里，如在这结束的loading事件，异步请求也适应在这里调用

3. mounted：挂载元素，获取到DOM节点

4. updated：如果对数据进行统一处理，在这里写上相应的函数

5. beforeDestory：可以弹出一个确认事件停止的确认框

6. nextTick：更新数据后立即操作dom

   

# v-show与v-if的区别

v-show是css切换，v-if是完整的销毁与重新创建

使用频繁切换时用v-show，运行较少改变时用v-if

v-if中如果值是false，那么该元素不会出现在Dom树中 不会产生这个html标签

v-show无论值是0/1 都会出现在DOM树中，v-show改变的只是css样式中dispaly的值

v-if控制元素的是否存在  v-show控制是否展示

# 开发中常用的指令：

v-model：一般用在表达输入，很轻松的实现表单控件和数据的双向绑定

v-html：更新元素的innerHTML

v-show与v-if：条件渲染，注意二者区别

v-on：click：可以简写成@click  @绑定一个事件。如果事件触发了，就可以指定事件的处理函数

v-for：基于原数据进行的循环渲染元素或者模板

v-bind：当表达式的值改变时，将其产生的连带影响，响应式的作用于DOM

v-bind：title=“msg”  简写的：      ：title=“msg”



# 绑定class的数组用法

对象方法 v-bind：class=“ {‘orange’：isRipe，‘green’：isNotRipe}”

数组方法v-bind：class=“[class1，class2]”

行内v-bind：style=“{color：color，fontSize：fontSize+‘px’}”

# 路由跳转方式

1. router-link标签会渲染为标签，template中的跳转就是这种
2. 另一种编辑是导航，也就是通过js跳转比如router，push（‘/home'）



# MVVM

M-model.model表示数据模型，也可以在mode中定义数据修改和操作的业务逻辑

V-view  view代表UI组件，他负责将数据模型转化为UI展示出来

VM-viewmdoel     viewModel监听模型数据的改变和控制视图行为。处理用户交互。简单理解就是一个同步View和model的对象，连接mode和view



# computed和watch有什么区别

**computed：**

computed是计算属性，也就是计算值，他更多运用于计算值的场景

computed具有缓冲性，computed的值在getter执行后是会缓存的，只有在他依赖的属性值

发生改变之后，下一次获取computed的值时重新调用相应的getter来计算

computed适用于计算比较消耗性能的计算场景

**watch**

watch更多的是观察的作用，类似于某些数据的监听回调，用于观察props $emit或者本组件的值，当数据变化时执行回调进行后续的操作

无缓存性，页面重新渲染时会执行（无论值是否变化）

**小结**

当我们要进行数值计算，而且依赖于其他数据，那么用computed

当你需要某一个数据变化时进行一些操作，，那么用watch来观察数据的变化





# vue组件中scoped属性的作用

style标签在加上scoped属性，表示他的样式应用于当下的模块，很好地实现了样式私有化的目的

但是得慎用  样式不易修改，很多时候，我们需要对公共组件的样式进行进行微调的



# 对于vue渐进式的理解

Vue的核心的功能，是一个视图模板引擎，但这不是说Vue就不能成为一个框架。如下图所示，这里包含了Vue的所有部件，在声明式渲染（视图模板引擎）的基础上，我们可以通过添加组件系统、客户端路由、大规模状态管理来构建一个完整的框架。更重要的是，这些功能相互独立，你可以在核心功能的基础上任意选用其他的部件，不一定要全部整合在一起。可以看到，所说的“渐进式”，其实就是Vue的使用方式，同时也体现了Vue的设计的理念 
在我看来，渐进式代表的含义是：主张最少

视图模板引擎
每个框架都不可避免会有自己的一些特点，从而会对使用者有一定的要求，这些要求就是主张，主张有强有弱，它的强势程度会影响在业务开发中的使用方式。
比如说，Angular，它两个版本都是强主张的，如果你用它，必须接受以下东西：
必须使用它的模块机制- 必须使用它的依赖注入- 必须使用它的特殊形式定义组件（这一点每个视图框架都有，难以避免）
所以Angular是带有比较强的排它性的，如果你的应用不是从头开始，而是要不断考虑是否跟其他东西集成，这些主张会带来一些困扰。
Vue可能有些方面是不如React，不如Angular，但它是渐进的，没有强主张，你可以在原有大系统的上面，把一两个组件改用它实现，当jQuery用；也可以整个用它全家桶开发，当Angular用；还可以用它的视图，搭配你自己设计的整个下层用。也可以函数式，都可以，它只是个轻量视图而已，只做了自己该做的事，没有做不该做的事，仅此而已。
**渐进式的含义，我的理解是：没有多做职责之外的事。**





# vue.js的两个核心是什么

**数据驱动**：Object.defineProperty和存储器属性：getter和setter可以称为基于依赖手机的观测机制，核心是VM 及ViewModel，保持数据与视图的一致性



**组件系统**





# vue常用修饰符

修饰符分为一般修饰符，事件修饰符，按键，系统

**一般修饰符**

.lazy :         v-model在每次的input时间触发后将输入框的值与数据进行同步。可以

用.lazy修饰符穿变为使用change事件进行同步

```js
<input v-model.lazy="mag">
```



.number

```js
<input v-model.number="age" type="number">
```

.trim

```js
//如果要自动过滤用户输入的首尾空白字符 
<input v-model.trim='trim'>
```

**事件修饰符**

```js
<a v-on:click.stop="doThis"></a><!-- 阻止单击事件继续传播 -->

<form v-on:submit.prevent="onSubmit"></form> <!-- 提交事件不再重载页面 -->

<a v-on:click.stop.prevent="doThat"></a> <!-- 修饰符可以串联 -->

<form v-on:submit.prevent></form>   <!-- 只有修饰符 -->

<div v-on:click.capture="doThis">...</div>   <!-- 添加事件监听器时使用事件捕获模式 --> <!-- 即元素自身触发的事件先在此处处理，然后才交由内部元素进行处理 -->

<div v-on:click.self="doThat">...</div>  <!-- 只当在 event.target 是当前元素自身时触发处理函数 --> <!-- 即事件不是从内部元素触发的 -->

<a v-on:click.once="doThis"></a> <!-- 点击事件将只会触发一次 -->
```





**按键修饰符**

```js
.enter
.tab
.delete (捕获“删除”和“退格”键)
.esc
.space
.up
.down
.left
.right
.ctrl
.alt
.shift
.meta
```

```js
<input v-on:keyup.enter="submit"> 或者 <input @keyup.enter="submit">
```

**系统修饰符**

```js
.ctrl
.alt
.shift
.meta
```

```js
<input @keyup.alt.67="clear"> 
    或者 
<div @click.ctrl="doSomething">Do something</div><!-- Ctrl + Click -->
```



# v-on可以监听多个方法吗（可以的）

一个元素绑定多个事件的两种写法，一个事件绑多个函数的两种写法

```js
<a style="cursor:default" v-on='{click:DoSomething,mouseleave:MouseLeave}'>doSomething</a>
```

两个事件

```js
<button @click="a(),b()">点我ab</button>
```

# vue中如何使用event对象

```js
<button @click="Event($event)">事    件对象</button>
```

# 让一个DOM显示，然后去获取这个元素的offsetWidth，会得到0，为什么

  把元素的show改为true ，元素并不会立即显示，理所当然的也不能获取到动态宽度。

正确做法是先把元素show出来，然后$nextTick去执行获取宽度的操作，

# vue组件中的data为做什么必须是函数

vue中的data值不能是对象，因为对象是引用类型，组件可能被多个实例同时使用，如果data值为对象，将导致多个实例贡献给一个对象，其中一个组件改变data属性值，其他实例也会受到影响





# vue中子组件调用父组件的方法

第一种方法是直接在子组件中通过this.$parent.envent来调用父组件的方法

第二种是在子组件中用$emit向父组件触发一个事件，父组件监听这个事件就行了

第三种就是

```js
<template>
  <div>
    <button @click="childMethod()">点击</button>
  </div>
</template>
<script>
  export default {
    props: {
      fatherMethod: {
        type: Function,
        default: null
      }
    },
    methods: {
      childMethod() {
        if (this.fatherMethod) {
          this.fatherMethod();
        }
      }
    }
  };
</script>
```

# vue中keep-alive在组件中的使用

keep-alive是vue的内置组件，可以使被包含的组件保留状态，或者避免被重新渲染

```js
<keep-alive>
  <component>
    <!-- 该组件将被缓存！ -->
  </component>
</keep-alive>
如果只想 router-view 里面某个组件被缓存


export default [
  {
    path: '/',
    name: 'home',
    component: Home,
    meta: {
      keepAlive: true // 需要被缓存
    }
  }, {
    path: '/:id',
    name: 'edit',
    component: Edit,
    meta: {
      keepAlive: false // 不需要被缓存
    }
  }
]
<keep-alive>
    <router-view v-if="$route.meta.keepAlive">
        <!-- 这里是会被缓存的视图组件，比如 Home！ -->
    </router-view>
</keep-alive>
 
<router-view v-if="!$route.meta.keepAlive">
    <!-- 这里是不被缓存的视图组件，比如 Edit！ -->
</router-view>
```





# 什么是vue的生命周期和生命周期钩子函数

**beforeCreated**：在市里初始化后，el和data没有初始化（在这个时期  this还不能使用，data中的数据，methods中的方法，watcher的时间也不能获得）

**created**：完成了data的数据初始化，el没有（可以对实例中的数据及各种方法进行操作，但是不能对DOM节点进行操作：没挂载呢）



**beforeMount**:完成el和data的初始化//这里的el是虚拟的DOM



**mounted**：完成了挂载，在这发起后端请求，拿回数据，配合路由钩子做一些事情（挂载完成，DOM节点被渲染到了DOM树中，一些需要dom的操作在这才能进行）



**beforeUpdate**：指view层数据发生变化前，不是data中的数据改变前 触发；



**update**：指view层数据改变之后



**beforeDestory**；你确认删除XX吗

**destoryed**：组件已被删除，清空相关的内容



什么是vue**的生命周期**

Vue 实例从创建到销毁的过程，就是生命周期。也就是从开始创建、初始化数据、编译模板、挂载Dom→渲染、更新→渲染、卸载等一系列过程，我们称这是 Vue 的生命周期。

vue**生命周期的作用**

它的生命周期有多个事件钩子,让我们在控制整个Vue实例的过程时更容易形成好的逻辑。









# vue单页面应用的优缺点

缺点：

不支持低版本的浏览器。只支持ie9以上

不利于SEO的优化

第一次加载首页相对耗时长一点

浏览器导航按钮不再可用    需自己实现



优点：

无刷新的体验，

不再以页面为单位，更多的是组件化的思想，代码结构和组织方式规范化，便于修改和调整

api共享，同一套的代码，直接可以运用到WEB界面  手机  平板等多种客户端

用户体验好。快  响应式刷新带来的是不需要重新加载整个页面



# 什么是computed（计算属性）

计算属性是需要复杂的逻辑 可以用method代替







# 组件传值：

```js
props：export default {
props: {

message: String //定义传值的类型<br>

},


//或者props:["message"]

data: {}

父组件调用子组件的方法：父组件   this.$refs.yeluosen.childMethod()


子组件向父组件传值并调用方法 $emit


组件之间：bus==$emit+$on
```

# vue-router的导航钩子，主要的作用就是拦截导航，往他完成跳转或者取消



全局的：前置钩子（beforeEach，afterEach） beforeResolve

单个路由独享的：beforeEnter

组件级的：beforeRouterEnter（不能获取组件实例的this）。beforeRouterUpdate，beforeRouteLeave



这是因为在执行路由钩子函数beforRouteEnter时候，组件还没有被创建出来；
先执行beforRouteEnter，再执行组件周期钩子函数beforeCreate，可以通过 next 获取组件的实例对象，如：next( (vm)=>{} )，参数vm就是组件的实例化对象。

# 完整的vue-router导航解析流程

1.导航被触发；
2.在失活的组件里调用beforeRouteLeave守卫；
3.调用全局beforeEach守卫；
4.在复用组件里调用beforeRouteUpdate守卫；
5.调用路由配置里的beforeEnter守卫；
6.解析异步路由组件；
7.在被激活的组件里调用beforeRouteEnter守卫；
8.调用全局beforeResolve守卫；
9.导航被确认；
10..调用全局的afterEach钩子；
11.DOM更新；
12.用创建好的实例调用beforeRouteEnter守卫中传给next的回调函数。

# vue-router的几种实例方法以及参数传递

name传递

to传递

采用url传递

# is 的用法（用于动态组件且基于Dom内模板的现值来工作）

is用来动态切换组件，DOM模板解析

```js
<table><tr is="my-row"></tr></table>
```

# vuex是什么？怎么使用？那些场景要用到它？



是什么：vuex框架中的状态管理模式有五种：state，getter，mutation，action，module

使用新建一个目录store

场景：单页面应用，组件之间的状态。音乐播放，登录状态，加入购物车



**vuex中state的特性：**

1. vuex就是一个仓库，仓库中放了很多对象，其中state就是数据源的存放地，对应于一般vue对象里面的data

2. state中存放的数据是响应式的，vue组件从store中读取数据，若是store中的数据发生改变，依赖这个数据的组件也会发生更新

3. 它通过mapState把全局的state和getters映射带当前组件的computed计算属性中

   

**vuex的getter的特性**

1. getters可以对state进行计算操作，他是store的计算属性

2. 虽然在组件内也可以做计算属性，但是getters可以在多组件中复用

3. 如果一个转台只在一个组件内使用，可以不用getters

   

**vuex中mutation特性**

1.改变store中state状态的唯一方法就是提交mutation，很类似事件

2.每个mutation都有一个字符串类型的事件类型和一个回调函数，我们需要改变state的值就要在回电函数中改变

3.我们要执行这个回调函数，那么我们就要执行相应的调用方法：store.commit



**Action** 类似于 mutation，不同在于：Action 提交的是 mutation，而不是直接变更状态；
Action 可以包含任意异步操作，Action 函数接受一个与 store 实例具有相同方法和属性的 context 对象，
因此你可以调用 context.commit 提交一个 mutation，
或者通过 context.state 和 context.getters 来获取 state 和 getters。
Action 通过 store.dispatch 方法触发：eg。
store.dispatch('increment')



**vuex的module特性**
Module其实只是解决了当state中很复杂臃肿的时候，module可以将store分割成模块，
每个模块中拥有自己的state、mutation、action和getter