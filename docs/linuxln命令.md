# Parent Node

- [ROOT](./root.md)
- [linux 命令](./linux命令.md)

# Child Node

# linux ln 命令

- `ln -b`: 如果目标目录中已经有同名的文件, 那么在覆盖之前先进行备份
- `ln -f`: 如果目标目录中已经有同名的文件, 无需提示, 直接覆盖
- `ln -i`: 人机交互, 如果目标目录中已经有同名的文件, 则提示是否进行覆盖
- `ln -n`: 把软链接视为一般目录(说明：范例中我会详细解释)
- `ln -s`: 创建软链接
- `ln -v`: 详细显示操作进行的步骤。(v 为 verbose 的意思)

```sh
ln -s /nodejs/bin/[包] /usr/local/bin/
```
