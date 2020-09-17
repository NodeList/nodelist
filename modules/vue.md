# Vue

## 原理

Vue 采用数据劫持配合发布者-订阅者模式，通过 Object.defineProperty() 来劫持各个属性的 getter 与 setter 方法，在数据发生变化的时候，发布消息给依赖收集器，去通知观察者，做出对应的回调函数去更新视图。

具体就是：
MVVM 作为绑定的入口，整合 Observe,Compil 和 Watcher 三者，通过 Observe 来监听 model 的变化
通过 Compil 来解析编译模版指令，最终利用 Watcher 搭起 Observe 和 Compil 之前的通信桥梁
从而达到数据变化 => 更新视图，视图交互变化(input) => 数据 model 变更的双向绑定效果。

## MVC、MVP、MVVM

### 1. MVC 模式：

视图（View）：用户界面。
控制器（Controller）：业务逻辑 view → controller → model → view
模型（Model）：数据保存
View 传送指令到 Controller； Controller 完成业务逻辑后，要求 Model 改变状态； Model 将新的数据发送到 View，用户得到反馈

### 2. MVP 模式：

将 Controller 改名为 Presenter，改变了通信方向。
view ⇋ Presenter ⇋ model
各部分之间的通信都是双向的
view 与 model 之间不发生联系，都通过 presenter 传递
view 非常薄，不部署任何业务逻辑，称为被动视图，即没有任何主动性，而 presenter 非常厚，所有逻辑都部署在那里

### 3. MVVM 模式：

Model–view–viewmodel：
Model：模型是指代表真实状态内容的领域模型（面向对象），或指代表内容的数据访问层（以数据为中心）
view：就像在 MVC 和 MVP 模式中一样，视图是用户在屏幕上看到的结构、布局和外观（UI）
viewmodel：视图模型是暴露公共属性和命令的视图的抽象
采用双向绑定，view 的变动，自动反映在 ViewModel。

## computed 与 watch 的区别

1. computed 是计算属性，依赖于其他属性去计算返回的值；watch 是侦听器，监听具体的某个值的变化去执行相应的方法。
2. computed 的值在执行 getter 后会缓存，只有当他的依赖属性值发生改变时才会重新调用 getter 方法计算新值；watch 只要监听到值的变化都会执行回调函数。
3. computed 通常只进行简单的计算并返回计算的结果；watch 的回调里会传入监听属性的新旧值。
