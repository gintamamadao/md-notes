# Parent Node

- [ROOT](./root.md)
- [CSS 学习杂记](./CSS学习杂记.md)

# Child Node

# css position 为 fixed 时设置 z-index 失效

- z-index 只有在设置了 position 为 relative,absolute,fixed 时才会有效。
- 谷歌浏览器在设置 position:fixed;后会触发元素创建一个新的层叠上下文，并且当成一个整体在父层叠上下文中进行比较
- 所以本来所有元素都在 root 内比较，改为 fixed 之后只能在父级元素内比较，而父级元素没有设置 z-index，所以无法比较。
- z-index 的“从父原则”。当你发现把 z-index 设的多大都没用时，看看其父元素是否设置了有效的 z-index
