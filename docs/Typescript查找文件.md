# Parent Node

- [ROOT](./root.md)
- [Typescript 语法](./Typescript语法.md)

# Child Node

# Typescript 查找文件

- 如果这个路径表示一个文件，如：foo.ts，采用该文件
- 否则，如果这个路径是一个文件夹，并且存在一个文件 foo/index.ts，采用该文件
- 否则，如果这个路径是一个文件夹，并且存在一个 foo/package.json 文件，在该文件中指定 types 的文件存在，采用该文件
- 否则，如果这个路径是一个文件夹，并且存在一个 package.json 文件，在该文件中指定 main 的文件存在，采用该文件
