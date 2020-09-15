# Vue Router

## 导航守卫

### router.beforeEach() 和 router.afterEach()

每个守卫方法接收三个参数：

to: Route: 即将要进入的目标 路由对象

from: Route: 当前导航正要离开的路由

next: Function: 一定要调用该方法来 resolve 这个钩子。

在项目中，一般在 beforeEach 这个钩子函数中进行路由跳转的一些信息判断。
判断是否登录，是否拿到对应的路由权限等等。
