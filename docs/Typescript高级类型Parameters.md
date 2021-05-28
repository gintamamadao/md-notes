# Parent Node

- [/](./root.md)
- [../](./Typescript类型推断infer.md)

# Child Node

# Detail

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
