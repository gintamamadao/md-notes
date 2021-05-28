# Parent Node

- [root](./root.md)
- [Typescript 语法](./Typescript语法.md)

# Child Node

- [Typescript 条件类型 extends](./Typescript条件类型extends.md)
- [Typescript 条件类型 infer](./Typescript条件类型infer.md)
- [Typescript 条件类型嵌套类型匹配](./Typescript条件类型嵌套类型匹配.md)

# Typescript 条件类型

- 条件类型是一种条件表达式进行类型的关系检测。

```js
type Equal<X, Y> = X extends Y ? true : false;

type Num = Equal<1, 1>; // true
type Str = Equal<'a', 'a'>; // true
type Boo = Equal<true, false>; // false
```
