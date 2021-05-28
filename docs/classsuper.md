# Parent Node

- [/](./root.md)
- [ECMAScript class](./ECMAScriptclass.md)

# Child Node

# Detail

- 调用父类的构造函数

```js
super();
```

- 返回当前上下文

```js
this === super();
```

- 可以调用父类上的方法

```js
super.functionOnParent();
```

- 在 super() 被调用之前, 子类是不能使用 this 的
