# Parent Node

- [root](./root.md)
- [ECMAScript 隐式转换](./ECMAScript隐式转换.md)

# Child Node

# toString 和 valueOf 有什么区别

- 当这两个函数同时存在时候，会先调用 valueOf ，若返回的不是原始类型，
- 那么会调用 toString 方法，如果这时候 toString 方法返回的也不是原始数据类型，
- 那么就会报错 TypeError: Cannot convert object to primitive value
