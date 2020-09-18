# CSS

## link 与 @import 的区别

-   link 是 XHTML 标签，除了加载 CSS 外，还可以定义 RSS 等其他事物；@import 属于 CSS 范畴，只加载 CSS。
-   link 引用 CSS 时，在页面加载的同时加载；@import 需要在网页完全载入以后加载。
-   link 是 XHTML 标签，无兼容问题；@import 是在 CSS2.1 提出的，低版本的浏览器不支持。
-   link 支持使用 Javascript 控制 DOM 去改变样式；而@import 不支持。

## 盒子模型

1. 普通盒模型

    - content(内容)：盒子的内容区域，显示文本和图像。
    - padding(内边距)：清除内容周围的区域，内边距是透明的。
    - border(边框)：围绕在内容和内边距外的边框。
    - margin(外边距)：清除边框外的区域，外边距是透明的。

    **总元素的宽度=宽度+左填充+右填充+左边框+右边框+左边距+右边距**
    **总元素的高度=高度+顶部填充+底部填充+上边框+下边框+上边距+下边距**

2. IE5 6 盒模型
    > width 是内容、内边距和边框的宽度的总和

## 选择器

`::before` 和 `:after` 中双冒号和单冒号的区别：

-   单冒号(:)用于 CSS3 伪类
-   双冒号(::)用于 CSS3 伪元素

-   CSS 伪类用于向某些选择器添加特殊的效果
-   CSS 伪元素用于将特殊的效果添加到某些选择器

## display

### display: none 与 visibility: hidden

-   区别：
-   重绘与回流

## position

## BFC
