# Parent Node

- [ROOT](./root.md)
- [docker 学习杂记](./docker学习杂记.md)

# Child Node

# docker 环境变量修改问题

- Dockerfile 中每一个指令都会建立一层，RUN 也不例外。
- 每一个 RUN 的行为，都会新建立一层，在其上执行这些命令，执行结束后，commit 这一层的修改，构成新的镜像。
- 上一次 RUN 造成的结果是不会影响到下一层的，除非是 ENV 或者 ARG 设置的环境变量
- ENV 和 ARG 并不支持赋值之外的命令