# Parent Node

- [ROOT](./root.md)
- [Sentry 知识体系](./Sentry知识体系.md)

# Child Node

# Sentry 配置

- release: string

  - release 标志了应用版本的唯一性，可以在 Sentry 平台上进行过滤指定的 release,
  - 能监控唯一版本的目的，建议配置为应用的版本号。

- enabled:boolean

  - 是否开启 Sentry 通信。如在本地开发时可关闭。

- environment: string

  - 应用环境。同一个应用同一个版本可能有多个运行环境，指定值也有助于区分应用环境。

- ignoreErrors: Array<string | RegExp>

  - 忽略的错误类型。对于一些特定的错误可以进行忽略而进行上报。

- integrations: Array<string>
  - Sentry 的集成插件，可以定制需要的插件功能。例如使用 CaptureConsole 来捕获控制台输出的错误信息。
  - 具体可参照 Integrations
