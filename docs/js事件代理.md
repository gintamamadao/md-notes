# Parent Node

- [/](./root.md)
- [ECMAScript 学习杂记](./ECMAScript学习杂记.md)

# Child Node

# Detail

- 在父元素设置监听事件
- 利用冒泡父元素可以获取事件
- 通过事件的 target 获取事件触发的元素

```html
<div id="parent">
  <button id="btn">click</button>
</div>
```

```js
let parent = document.getElementById("parent");
parent.addEventListener("click", function (e) {
  if (e.target.id == "btn") {
    //do something
  }
});
```
