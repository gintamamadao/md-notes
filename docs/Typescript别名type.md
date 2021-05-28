# Parent Node

- [/](./root.md)
- [Typescript 类型声明](./Typescript类型声明.md)

# Child Node

# Detail

- 类型别名会给一个类型起个新名字。
- 类型别名有时和接口很像，但是可以作用于原始值，联合类型，元组以及其它任何你需要手写的类型

```ts
type Name = string;
type NameResolver = () => string;
type NameOrResolver = Name | NameResolver;
```
