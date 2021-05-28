# Parent Node

- [root](./root.md)
- [Typescript 语法](./Typescript语法.md)

# Child Node

- [Typescript 类型继承 extends](./Typescript类型继承extends.md)

# Typescript 类型继承

- 和类一样，接口也可以相互继承。
- 这让我们能够从一个接口里复制成员到另一个接口里，可以更灵活地将接口分割到可重用的模块里。
- 一个接口可以继承多个接口，创建出多个接口的合成接口

```ts
interface Shape {
  color: string;
}

interface Square extends Shape {
  sideLength: number;
}
interface Square extends Shape, PenStroke {
  sideLength: number;
}
```
