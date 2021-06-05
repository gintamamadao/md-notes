# Parent Node

- [ROOT](./root.md)
- [ECMAScript 解构](./ECMAScript解构.md)

# Child Node

# js 数组模型的解构

## 基本

```js
let [a, b, c] = [1, 2, 3];
// a = 1; b = 2; c = 3;
```

## 可嵌套

```js
let [a, [[b], c]] = [1, [[2], 3]];
// a = 1; b = 2; c = 3;
```

## 可忽略

```js
let [a, , b] = [1, 2, 3];
// a = 1; b = 3
```

## 不完全解构

```js
let [a = 1, b] = [];
// a = 1, b = undefined
```

## 剩余运算符

```js
let [a, ...b] = [1, 2, 3];
//a = 1; b = [2, 3]
```

## 字符串等

> 解构的目标若为可遍历对象, 皆可进行解构赋值

```js
let [a, b, c] = "hel";
// a = 'h'; b = 'e'; c = 'l'
```

## 解构默认值

```js
let [a = 2] = [undefined]; // a = 2
let [a = 3, b = a] = []; // a = 3, b = 3
let [a = 3, b = a] = [1]; // a = 1, b = 1
let [a = 3, b = a] = [1, 2]; // a = 1, b = 2
```
