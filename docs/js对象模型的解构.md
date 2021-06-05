# Parent Node

- [ROOT](./root.md)
- [ECMAScript 解构](./ECMAScript解构.md)

# Child Node

# js 对象模型的解构

## 基本

```js
let { foo, bar } = { foo: "aaa", bar: "bbb" };
// foo = 'aaa'; bar = 'bbb'
let { baz: foo } = { baz: "ddd" };
// foo = 'ddd'
```

## 可嵌套

```js
let {
  p: [x, { y }],
} = { p: ["hello", { y: "world" }] };
// x = 'hello'; y = 'world'
```

## 可忽略

```js
let {
  p: [x, {}],
} = { p: ["hello", { y: "world" }] };
// x = 'hello'
```

## 不完全解构

```js
let {
  p: [{ y }, x],
} = { p: [{ y: "world" }] };
// x = undefined; y = 'world'
```

## 剩余运算符

```js
let { a, b, ...rest } = { a: 10, b: 20, c: 30, d: 40 };
// a = 10; b = 20; rest = {c: 30, d: 40}
```

## 解构默认值

```js
let { a = 10, b = 5 } = { a: 3 };
// a = 3; b = 5;
let { a: aa = 10, b: bb = 5 } = { a: 3 };
// aa = 3; bb = 5;
```
