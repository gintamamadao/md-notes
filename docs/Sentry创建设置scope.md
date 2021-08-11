# Parent Node

- [ROOT](./root.md)
- [Sentry 知识体系](./Sentry知识体系.md)

# Child Node

# Sentry 创建设置 scope

- scope 信息包括 ：user 、tags 、level、fingerprint、extra data
- 推送范围时，它会继承父范围内的所有数据，并在弹出时恢复所有修改。
- 当您在内部调用诸如 capture_event 之类的全局函数时，Sentry 会发现当前中心并要求它捕获事件。
- 然后，内部中心将事件与最高范围的数据合并。

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
