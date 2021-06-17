# Parent Node

- [ROOT](./root.md)
- [yalc](./yalc.md)

# Child Node

# yalc 发布依赖

- 在所开发的依赖项目下执行发布操作

```sh
yalc publish
```

- 此时如果存在 npm 生命周期脚本：prepublish、prepare、prepublishOnly、prepack、preyalcpublish，
- 会按此顺序逐一执行。如果存在：postyalcpublish、postpack、publish、postpublish，也会按此顺序逐一执行。

想要完全禁用脚本执行需要使用

```sh
yalc publish --no-scripts
```

- 此时就已经将依赖发布到本地仓库了。
- 当有新修改的包需要发布时，使用推送命令可以快速的更新所有依赖

```sh
yalc publish --push
yalc push // 简写
```

- 参数:

  - `--changed`，快速检查文件是否被更改
  - `--replace`，强制替换包
