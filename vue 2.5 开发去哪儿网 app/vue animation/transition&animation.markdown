动画和过渡中的几个知识点：
css 实现过渡和动画
1. vue 能够自动封装被 `transition` 包裹的元素，并为其添加控制动画的类名：v-enter、v-enter-active、v-enter-to,对应离开的类名把 enter 换成 leave 即可。当 transition 有属性 `name` 的时候，Vue 会将前面类名中的 v 替换成 name 的属性值。
2. 使用 css 属性 `transition` 定义过渡，使用 `animation` 和 `@keyframes` 定义动画
3. css 动画的库：[animate.css](https://github.com/daneden/animate.css)
4. 多个元素或者组件使用动画，可为 `transition` 包裹元素添加属性： `mode`，确定过渡的模式： `in-out/out-in`。多个**相同的**元素要有动画效果，要为元素添加 `key` 值，在 vue 中对于相同的元素在替换的时候为了性能考虑，会复用元素，只替换元素里面的内容。
5. 初始渲染的时候要添加动画：要为 `transition` 添加 `appear` 属性，然后在 css 中写类：`.appear / .appear-to / .appear-active` 的样式
6. 可在 `transition` 元素内自定义过渡类名：`enter-class/enter-to-class/enter-active-class`，`leave` 和 `appear` 同理
7. 同时添加过渡和动画的时候：自定义 `enter-active-class` 的类名：" animated swing"(使用了 animated 的 css 库)，再为 `enter-active-class` 添加自定义类名定义过渡效果。为 `transition` 添加 `type` 属性确定以哪个动画的执行时间为整个动画的执行时长。或者添加 `duration` 属性自定义动画执行的总时长
8. 列表的动画和过渡，在列表外层包裹一个 `<transition-group>` 即可，使用方法同 `<transition>`。

js 实现过渡和动画
1. js 的动画库：[Velocity.js](http://www.velocityjs.org/)
2. 针对过渡元素有很多的事件监听，可以在事件处理函数中实现动画或者其他的逻辑。事件有： `before-enter`、`enter`、`after-enter`、`enter-cancelled `，`leave` 和 `appear` 的事件为事件名里的 `enter` 换成 `leave` 或 `appear` 即可
