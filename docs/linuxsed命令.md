# Parent Node

- [ROOT](./root.md)
- [linux 命令](./linux命令.md)

# Child Node

# linux sed 命令

- sed 是 Linux 下一款功能强大的非交互流式文本编辑器，
- 可以对文本文件进行增、删、改、查等操作，支持按行、按字段、按正则匹配文本内容，灵活方便，特别适合于大文件的编辑

```sh
sed -e 's/wang/w/g;s/xu/x/g' user.txt,
```

- 's/wang/w/g;s/xu/x/g'的意思，s 代表 search，g 全局匹配，
- 因而意思是将 user.text 文本中所有的 wang 替换成 w, xu 替换成 x
