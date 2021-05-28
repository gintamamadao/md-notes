# Parent Node

- [root](./root.md)
- [ECMAScript 隐式转换](./ECMAScript隐式转换.md)

# Child Node

# Detail

- 基本类型直接返回，基本类型的值
- 对象
  - 如果对象的 ValueOf 方法的结果是原始值，返回原始值。
  - 如果对象的 toString 方法返回原始值，就返回这个值；
- 其他情况都返回一个错误
