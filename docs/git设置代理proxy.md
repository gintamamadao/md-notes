# Parent Node

- [ROOT](./root.md)
- [git 学习杂记](./git学习杂记.md)

# Child Node

# git 设置代理 proxy

```sh
git config --global http.proxy http://127.0.0.1:1080
git config --global https.proxy http://127.0.0.1:1080
```

- 如果安装 github 上的依赖安装不上的话可以试一下设置代理
- 系统装依赖不代表 git 也走依赖

- 取消代理：

```sh
git config --global --unset http.proxy
git config --local --unset http.proxy
```
