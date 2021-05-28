# Parent Node

- [/](./root.md)
- [../](./Typescript类型推断infer.md)

# Child Node

# Detail


```ts
/**
 * Obtain the return type of a function type
 */
type ReturnType<T extends (...args: any) => any> = T extends (...args: any) => infer R ? R : any;
```