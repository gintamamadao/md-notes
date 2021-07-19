# Parent Node

- [ROOT](./root.md)
- [npm 学习杂记](./npm学习杂记.md)

# Child Node

# npm pkg 依赖配置

### 1.依赖包名称:VERSION

- 这是最常见的依赖配置，VERSION 是一个遵循 SemVer 规范的版本号配置，npm install 时将到 npm 服务器下载符合指定版本范围的包。

### 2.依赖包名称:DWONLOAD_URL

- 包名称后面放上包的下载地址，DWONLOAD_URL 是一个可下载的 tarball 压缩包地址，模块安装时会将这个.tar 下载并安装到本地。

### 3.依赖包名称:LOCAL_PATH

- LOCAL_PATH 是一个本地的依赖包路径，例如 file:../pacakges/pkgName。适用于你在本地测试一个 npm 包，不应该将这种方法应用于线上。

### 4.依赖包名称:GITHUB_URL

- GITHUB_URL 即 github 的 username/modulename 的写法，例如：ant-design/ant-design，你还可以在后面指定 tag 和 commit id。

### 5.依赖包名称:GIT_URL

- GIT_URL 即我们平时 clone 代码库的 git url，也就是我第二个方案中使用的 git \*\*\*.git
