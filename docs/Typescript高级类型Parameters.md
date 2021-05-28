# Parent Node

- [root](./root.md)
- [Typescript 条件类型 infer](./Typescript条件类型infer.md)

# Child Node

# Typescript 高级类型 Parameters

```ts
/**
 * Obtain the parameters of a function type in a tuple
 */
type Parameters<T extends (...args: any) => any> = T extends (
  ...args: infer P
) => any
  ? P
  : never;
```
