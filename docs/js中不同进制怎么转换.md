# Parent Node

- [/](./root.md)
- [../](./ECMAScript学习杂记.md)
- [../](./NumbertoString.md)

# Child Node

# Detail

```js
numObj.toString([radix]);
```

- 指定要用于数字到字符串的转换的基数(从 2 到 36)。如果未指定 radix 参数，则默认值为 10。
- Number 对象覆盖了 Object 对象上的 toString() 方法，
- 它不是继承的 Object.prototype.toString()。
- 对于 Number 对象，toString() 方法以指定的基数返回该对象的字符串表示。
