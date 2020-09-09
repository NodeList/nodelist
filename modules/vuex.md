# Vuex

> 每一个 Vuex 应用的核心就是 store（仓库）

### Vuex 与单纯的全局对象有以下两点不同：

1. Vuex 的状态存储是响应式的。当 Vue 组件在 store 中读取状态时，若 store 中的状态发生变化，那么相应的组件也会相应的得到高效更新。
2. 不能直接改变 store 中的状态。改变 store 中状态的唯一路径就是显式地 **提交（commit） `mutation`**, \*\*这样做的目的是我们需要明确地追踪到状态的变化

### 创建简单的 store

```javascript
import Vue from "vue";
import Vuex from "vuex";

Vue.use(Vuex);

const store = new Vuex.Store({
    state: {
        count: 0,
    },
    mutations: {
        increment(state) {
            state.count++;
        },
    },
});

// 通过 store.state 来获取状态对象
console.log(store.state.count); // 0
// 通过 store.commit 方法触发状态变更
store.commit("increment");
console.log(store.state.count); // 1
```

为了在 Vue 组建中访问 `this.$store` prototype, 需要为 Vue 示例创建好的 store。Vuex 提供了一个从根组件向所有子组件，以 `store` 选项的方式“注入”该 store 的机制：

```js
new Vue({
    el: "#app",
    store: store,
    // 使用 ES6
    store,
});
```

由于 store 中的状态是响应式的，在组件中调用 store 中的状态简单到仅需要在计算属性中返回即可。触发变化也仅仅是在组件的 methods 中提交 mutation。

### 1. State

> 单一状态树

### 2. Getter

> 可以认为是 store 的计算属性

### 3. Matation

> 类似于事件

### 4. Action

### 5. Module
