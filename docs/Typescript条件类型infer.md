# Parent Node

- [root](./root.md)
- [Typescript 条件类型](./Typescript条件类型.md)

# Child Node

- [Typescript 高级类型 Parameters](./Typescript高级类型Parameters.md)
- [Typescript 高级类型 ReturnType](./Typescript高级类型ReturnType.md)
- [Typescript 高级类型 InstanceType](./Typescript高级类型InstanceType.md)

# Typescript 条件类型 infer

- 使用 infer 声明一个类型变量，在 条件类型判定为 true 时生效

```ts
type ExtractArrayItemType<T> = T extends (infer U)[] ? U : T;

// 条件判断都为 false，返回 T
type T1 = ExtractArrayItemType<string>; // string
type T2 = ExtractArrayItemType<() => number>; // () => number
type T4 = ExtractArrayItemType<{ a: string }>; // { a: string }

// 条件判断为 true，返回 U
type T3 = ExtractArrayItemType<Date[]>; // Date
```

- infer U 语句就是声明一个类型变量 U（它可以是任意类型，取决于 T），变量 U 会解析 T 类型。
