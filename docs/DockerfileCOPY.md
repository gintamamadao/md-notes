# Parent Node

- [ROOT](./root.md)
- [docker Dockerfile](./dockerDockerfile.md)

# Child Node

# Dockerfile COPY

- 将本地文件添加入镜像
- 接受两个参数第一个是在本地文件夹，一个是在镜像中的文件夹
- 说明当前工作目录并不会直接被打包成镜像，只是将当前工作目录当成要打包的文件的池
- 这个命令的路径都是用于镜像和外面交流的，如果只是镜像内操作用 RUN cp 执行相关操作
