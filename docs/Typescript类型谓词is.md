# Parent Node

- [/](./root.md)
- [Typescript 语法](./Typescript语法.md)

# Child Node

# Detail

```ts
function isFish(pet: Fish | Bird): pet is Fish {
  return (<Fish>pet).swim !== undefined;
}
```

- 在这个例子里， pet is Fish 就是类型谓词。 谓词为 parameterName is Type 这种形式， parameterName 必须是来自于当前函数签名里的一个参数名

```ts
if (isFish(pet)) {
  pet.swim();
} else {
  pet.fly();
}
```

- 这样 TypeScript 不仅知道在 if 分支里 pet 是 Fish 类型； 它还清楚在 else 分支里，一定 不是 Fish 类型，一定是 Bird 类型
- 这样就叫类型保护
