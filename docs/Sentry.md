# Parent Node

- [ROOT](./root.md)
- [ECMAScript 插件依赖](./ECMAScript插件依赖.md)

# Child Node

- [Sentry 知识体系](./Sentry知识体系.md)
- [Sentry 学习杂记](./Sentry学习杂记.md)

# Sentry

- 配置例子

```js
// SentryErrorBoundary
import React, { Component } from "react";
import * as Sentry from "@sentry/browser";

Sentry.init({
  dsn: "YOUR_DSN_KEY_HERE",
});

class SentryErrorBoundary extends Component<any, any> {
  componentDidCatch(error, errorInfo): void {
    Sentry.withScope((scope) => {
      scope.setExtras(errorInfo);
      Sentry.captureException(error);
    });
  }

  render() {
    return this.props.children;
  }
}

export default SentryErrorBoundary;
```
