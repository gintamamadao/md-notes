# Parent Node

- [ROOT](./root.md)
- [bash shell 知识体系](./bashshell知识体系.md)

# Child Node

# bash shell 命令替换

- 在 bash 中，$( )与\` \`（反引号）都是用来作命令替换的。
- 命令替换与变量替换差不多，都是用来重组命令行的，先完成引号里的命令行，
- 然后将其结果替换出来，再重组成新的命令行。

```sh
[root@localhost ~] echo today is $(date "+%Y-%m-%d")
today is 2017-11-07
[root@localhost ~] echo today is `date "+%Y-%m-%d"`
today is 2017-11-07
```

- $( )与 \` \` 在操作上，这两者都是达到相应的效果，但是建议使用$( )，理由如下：
- \` \` 很容易与''搞混乱，尤其对初学者来说，而$( )比较直观。
- 最后，$( )的弊端是，并不是所有的类 unix 系统都支持这种方式，但反引号是肯定支持的。
