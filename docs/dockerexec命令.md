# Parent Node

- [ROOT](./root.md)
- [docker 命令](./docker命令.md)

# Child Node

# docker exec 命令

```sh
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```

- `-d` :分离模式: 在后台运行

- `-i` :即使没有附加也保持 STDIN 打开

- `-t` :分配一个伪终端

- 例子

```sh
docker exec -it mysql /bin/bash
```
