# Parent Node

- [ROOT](./root.md)
- [docker Dockerfile](./dockerDockerfile.md)

# Child Node

# Dockerfile ADD

- 将本地文件添加到容器中，tar 类型文件会自动解压(网络压缩资源不会被解压)，可以访问网络资源，类似 wget

```sh
ADD hom* /mydir/ # 添加所有以"hom"开头的文件
ADD hom?.txt /mydir/ # ? 替代一个单字符,例如："home.txt"
ADD test relativeDir/ # 添加 "test" 到 `WORKDIR`/relativeDir/
ADD test /absoluteDir/ # 添加 "test" 到 /absoluteDir/
```
