# Parent Node

- [ROOT](./root.md)
- [Sentry 知识体系](./Sentry知识体系.md)

# Child Node

# Sentry api

- `captureException(exception)` : 捕获一个 js 异常，传入一个 exception 对象或者类对象。

- `captureMessage(message,level) `: 捕获一条信息，传入信息内容和信息级别

- `captureEvent(sentryEvent) `: 捕获一个事件，sentryEvent 是手动创建的，自定义的

- `addBreadcrumb(Breadcrumb) `： 添加一个面包屑，以供接下里的捕获

- `configureScope((scope)=>{})` : 设置 context 信息到 scope 上面

- `withScope((scope)=>{})` : 设置一个临时的 scope 信息到 context 上面

- `setUser` : 通过 setUser 来设置 User 信息。其中 user 可以设置的信息包括 id、username、ip_address、email

- `setTag` : tags 是给事件定义不同的键/值对，可以在查找的时候更容易。

- `setLevel` : 通过这个来设置事件的严重性。

- `addBreadcrumb` :面包屑用于记录一系列当行为，当下一次发生错误事件上传当时候会随着一起上报。浏览器 javascript sdk 将自动记录所有当位置更改。

- `showReportDialog`: 用户反馈，sentry 提供了一个客户反馈当窗口。
