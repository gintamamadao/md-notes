# Parent Node

- [ROOT](./root.md)
- [Typescript 学习杂记](./Typescript学习杂记.md)

# Child Node

# ts 将可能为 undefined 的类型结合到另一个类型

```ts
export type Query<T> = T extends void | undefined | null | never
  ? Query
  : T & Query;
```

- T 通过 extends 判断是否符合约束 void | undefined | null | never
- 是就返回 Query， 不是就返回 T & Query
