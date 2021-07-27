# Parent Node

- [ROOT](./root.md)
- [docker 学习杂记](./docker学习杂记.md)

# Child Node

# docker 的退出机制

- Docker 容器启动时，默认会把容器内部第一个进程，也就是 pid=1 的程序，作为 docker 容器是否正在运行的依据，
- 如果 docker 容器 pid=1 的进程挂了，那么 docker 容器便会直接退出。
- 以 nginx 为例子
- nginx 默认是以后台模式启动的，Docker 未执行自定义的 CMD 之前，nginx 的 pid 是 1，执行到 CMD 之后，nginx 就在后台运行，
- bash 或 sh 脚本的 pid 变成了 1。
- 所以一旦执行完自定义 CMD，nginx 容器也就退出了。
- 为了保持 nginx 的容器不退出，应该关闭 nginx 后台运行
