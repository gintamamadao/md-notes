# Parent Node

- [ROOT](./root.md)
- [ECMAScript 学习杂记](./ECMAScript学习杂记.md)

# Child Node

# location.replace 和 location.href 的区别

- window.location.replace 和 window.location.href 都可以实现页面的跳转，
- 但是它们是有区别的，两者后退时所回退的页面不一样
- 假如有三个页面 a b c
- 按照页面的跳转顺序是 a => b => c

  - b => c 在从页面 b 跳转到页面 c 时，如果是通过 window.location.href("…/c")
    此时 b 页面的路径会被 c 页面代替，但是点击回按钮后页面回退的是 b 页面
  - b =>c 在从页面 b 跳转到页面 c 时，如果是通过 window.location.replace("…/c")
    此时 b 页面的路径会被 c 页面代替，但是点击回按钮后页面回退的是 a 页面（最开始的页面）
    两者的区别:
