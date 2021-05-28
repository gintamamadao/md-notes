# Parent Node

- [root](./root.md)
- [ECMAScript 变量声明](./ECMAScript变量声明.md)
- [ECMAScript 作用域](./ECMAScript作用域.md)

# Child Node

- [js LHS 查询](./jsLHS查询.md)
- [js RHS 查询](./jsRHS查询.md)
- [js 在未声明的变量不同查询的区别](./js在未声明的变量不同查询的区别.md)

# js 变量查询

- LHS(Left-hand Side)引用和 RHS(Right-hand Side)引用。
- 通常是指等号（赋值运算）的左右边的引用。

```js
console.log(a);
```

- 这里对 a 的引用是一个 RHS 引用，因为这里 a 并没有赋予任何值，我们只是想查找并取得 a 的值，然后将它打印出来。

```js
a = 2;
```

- 这里对 a 的引用是一个 LHS 引用，因为我们并不关心当前的值是什么，只是想要为赋值操作找到目标。
