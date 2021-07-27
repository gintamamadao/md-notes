# Parent Node

- [ROOT](./root.md)
- [docker 命令](./docker命令.md)

# Child Node

# docker push 命令

- 将本地的镜像上传到镜像仓库,要先登陆到镜像仓库

```sh
docker push [OPTIONS] NAME[:TAG]
```

- TAG 就是版本号，可以没有，没有的话默认为 :lasted
- push 可以指定 hub， 需要在 name 前面加上，则 NAME 为 \[hub_url]/\[name]
