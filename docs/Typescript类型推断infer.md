# Parent Node

- [/](./root.md)
- [../](./Typescript语法.md)

# Child Node

- [Typescript 高级类型 Parameters](./Typescript高级类型Parameters.md)
- [Typescript 高级类型 ReturnType](./Typescript高级类型ReturnType.md)
- [Typescript 高级类型 InstanceType](./Typescript高级类型InstanceType.md)

# Detail

- infer 表示在 extends 条件语句中待推断的类型变量

```ts
type ParamType<T> = T extends (param: infer P) => any ? P : T;
```

- 在这个条件语句 T extends (param: infer P) => any ? P : T 中，infer P 表示待推断的函数参数。
- 整句表示为：如果 T 能赋值给 (param: infer P) => any，则结果是 (param: infer P) => any 类型中的参数 P，否则返回为 T。

```ts
interface User {
  name: string;
  age: number;
}

type Func = (user: User) => void;

type Param = ParamType<Func>; // Param = User
type AA = ParamType<string>; // string
```
