# JavaScript
JavaScript有以下三部分组成：
> - ECMAScript(核心)：ECMAScript提供核心语言功能 
> - 文档对象模型(DOM)：DOM提供访问和操作网页内容的方法和接口
> - 浏览器对象模型(BOM)：BOM提供与浏览器交互的方法和接口
## ECMAScript
> 语法  类型  语句  关键字  保留字  操作符  对象

### 数据类型
#### 基本数据类型
```Undefined``` ```Null``` ```Boolean``` ```Number``` ```String``` ```Symbol```
#### 引用类型

## 文档对象模型(DOM)
> DOM!级  DOM2级  DOM3级
## 浏览器对象模型(BOM)
> window对象  location对象  navigator对象  screen对象  history对象
## 数据类型

-   **基本数据类型：** `string, number, Boolean, undefined, null, symbol`
-   **引用类型:** `object`

## 浅拷贝与深拷贝

## typeof 与 instanceof

### typeof

测试变量的类型，返回一个字符串，包括：`number`, `boolean`, `string`, `function`, `object`, `undefined`。

### instanceof

判断一个变量是否是某个对象的实例，返回 Boolean 类型：`true`, `false`。

```javascript
window instanceof Object; // false
typeof window; // object
```

> instanceof 测试的 object 是 es 语法中的对象，不是指 dom 模型对象

## 原型

### 1. 原型

每个构造函数都有一个 `prototype`(原型)（箭头函数以及 Function.prototype.bind() 没有该属性）属性，是一个指针，指向一个对象（原型对象），该对象包含实例所共享的所有方法与属性，也可理解为原型对象是用来给实例共享属性和方法的。
所有原型对象都会自动获得一个 `constructor` 属性，该属性包含一个指向 `prototype` 属性所在函数（构造函数？）的指针
创建实例时，每个实例会包含一个 `[[Prototype]](__proto__)` 属性，指向构造函数的原型对象。

> 连接存在于构造函数的原型对象与实例之间，而不是存在于实例与构造函数之间。

-   `prototype` 是构造函数的属性，指向该函数的原型对象；
-   `constructor` 是原型对象的属性，指向构造函数；
-   `[[Prototype]](__proto__)` 是实例与原型对象的属性，指向原型对象。

### 2. 原型链

每个对象都有一个 `__proto__` 属性，指向原型对象，当某个对象访问某个属性或某个方法时，会先去自己指向的原型对象中去查找，若找到则终止，否则继续从自己指向的原型对象指向的原型对象中去查找，以此类推，直到指向 `null`(即直到查找到 Object )，这就是原型链。

## 闭包

闭包是指有权访问另一个函数作用域中变量的函数。当在函数内部定义了函数时，就定义了闭包，内部函数可以引用外部函数的变量，从而导致垃圾回收机制不能回收当前变量，这会导致内存泄漏。
