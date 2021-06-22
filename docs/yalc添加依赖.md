# Parent Node

- [ROOT](./root.md)
- [yalc](./yalc.md)

# Child Node

# yalc 添加依赖

- 进入到项目执行

```sh
yalc add [my-package]
```

- 可以看到项目中添加了 yalc.lock 文件，package.json 对应的包名会有个地址为 file:.yalc/开头的项目。
- 也可以使用

```sh
yalc add [my-package@version]
```

- 将版本锁定，避免因为本地新包推送产生影响。

- 参数:

  - `--dev`，将依赖添加进 dependency 中
  - `--pure`，不会影响 package.json 文件
  - `--link`，使用 link 方式引用依赖包，yalc add \[my-package] --link
  - `--workspace` (or -W)，添加依赖到 workspace:协议中
