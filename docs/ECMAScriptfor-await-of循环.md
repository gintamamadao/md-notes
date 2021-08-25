# Parent Node

- [ROOT](./root.md)
- [ECMAScript 循环遍历](./ECMAScript循环遍历.md)

# Child Node

# ECMAScript for-await-of 循环

- 语法

```js
for await (variable of iterable) {
  statement;
}
```

- variable
  - 在每次迭代中，将不同属性的值分配给变量。
  - 变量有可能以 const, let, 或者 var 来声明。
- iterable
  - 被迭代枚举其属性的对象。
  - 与 for...of 相比，这里的对象可以返回 Promise，如果是这样，那么 variable 将是 Promise 所包含的值，否则是值本身。

- 例子

```js
async function* asyncGenerator() {
  var i = 0;
  while (i < 3) {
    yield i++;
  }
}

(async function () {
  for await (num of asyncGenerator()) {
    console.log(num);
  }
})();
```
