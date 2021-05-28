# Parent Node

- [root](./root.md)
- [js 闭包使用场景](./js闭包使用场景.md)

# Child Node

# js 闭包实现数据双向绑定简单例子

```js
function createCache() {
  const data = {};
  // 闭包中的数据，被隐藏，不被外界访问
  return {
    set: function (key, val) {
      data[key] = val;
    },
    get: function (key) {
      return data[key];
    },
  };
}
```
