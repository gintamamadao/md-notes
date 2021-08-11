# Parent Node

- [ROOT](./root.md)
- [Sentry 知识体系](./Sentry知识体系.md)

# Child Node

# Sentry 额外信息上报

- 当前 Sentry 除了上报错误信息之外，还包括一些基本的浏览器信息和系统信息，
- 除此之外，还可以额外自定义一些信息进行上报。
- 提供这一能力的称为 Scope。其可以包含 user、tags、level、fingerprint、extra data 等丰富信息，
- 分别通过 scope.setUser、scope.setTags 、scope.setLevel、scope.setFingerprint、scope.setExra 调用。
- 我们可以将用户的相关信息进行上报，将上报的错误与用户关联起来，当用户遇到线上故障的时候，我们就能够在 Sentry 后台利用用户的 ID 来搜索得到用户遇到了哪些错误。

```js
// 设置用户信息：
scope.setUser({ “email”: “xx@xx.cn”})
// 给事件定义标签：
scope.setTags({ ‘api’, ‘api/ list / get’})
// 设置事件的严重性：
scope.setLevel(‘error’)
// 设置事件的分组规则：
scope.setFingerprint(['{{ default }}', url])
// 设置附加数据：
scope.setExtra(‘data’, { request: { a: 1, b: 2 })
```

- 创建 scope 有两种方式：

  - 全局 scope
  - 局部 scope

- 全局 scope 通过 Sentry.configureScope 创建：

```js
Sentry.configureScope(function (scope) {
  scope.setTag("my-tag", "my value");
  scope.setUser({
    id: 42,
    email: "john.doe@example.com",
  });
});
```

- 创建后，应用的所有的错误都被关联到当前 scope 信息。
- 局部 scope 通过 Sentry.withScope 创建：


```js
Sentry.withScope(function (scope) {
  scope.setTag("my-tag", "my value");
  scope.setLevel("warning");
  // will be tagged with my-tag="my value"
  Sentry.captureException(new Error("my error"));
});

// will not be tagged with my-tag
Sentry.captureException(new Error("my other error"));
```