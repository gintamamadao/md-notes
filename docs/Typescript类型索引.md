# Parent Node

- [root](./root.md)
- [Typescript 语法](./Typescript语法.md)

# Child Node

# Typescript 类型索引

```ts
function getProperty<T, K extends keyof T>(o: T, name: K): T[K] {
  return o[name]; // o[name] is of type T[K]
}
```

- 索引值类型访问， 在这里，类型语法反映了表达式语法。
- 就像索引类型查询一样，你可以在普通的上下文里使用 T\[K]，表示某一个 key 的类型
- 你只要确保类型变量 K extends keyof T 就可以了
