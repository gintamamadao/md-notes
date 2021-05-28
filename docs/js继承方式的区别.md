# Parent Node

- [/](./root.md)
- [ECMAScript 学习杂记](./ECMAScript学习杂记.md)

# Child Node

# Detail

```js
function child() {}
function parent() {}
//1.
child.prototype.__proto__ = parent.prototype;
//2.
child.prototype = new parent();
```

- 方法 2 具有副作用，会影响 prototype 的 contrustor 的指向
