# Parent Node

- [ROOT](./root.md)
- [Sentry 知识体系](./Sentry知识体系.md)

# Child Node

# Sentry DSN

- DSN是连接客户端(项目)与sentry服务端,让两者能够通信的钥匙；
- 每当我们在sentry服务端创建一个新的项目，都会得到一个独一无二的DSN，也就是密钥。
- 在客户端初始化时会用到这个密钥，这样客户端报错，服务端就能抓到你对应项目的错误了。
- 之前版本的sentry对于密钥分为公钥和私钥，一般前端用公钥(DSN(Public))，但是现在的版本舍弃了这种概念，只提供了一个密钥。
