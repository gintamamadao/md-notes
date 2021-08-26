# Parent Node

- [ROOT](./root.md)
- [linux 命令](./linux命令.md)

# Child Node

# linux xargs 命令

- xargs（英文全拼： eXtended ARGuments）是给命令传递参数的一个过滤器，也是组合多个命令的一个工具。
- xargs 可以将管道或标准输入（stdin）数据转换成命令行参数，也能够从文件的输出中读取数据。
- xargs 也可以将单行或多行文本输入转换为其他格式，例如多行变单行，单行变多行。
- xargs 默认的命令是 echo，这意味着通过管道传递给 xargs 的输入将会包含换行和空白，不过通过 xargs 的处理，换行和空白将被空格取代。
- xargs 是一个强有力的命令，它能够捕获一个命令的输出，然后传递给另外一个命令。

### 参数

- `-a` file 从文件中读入作为 stdin
- `-e` flag ，注意有的时候可能会是-E，flag 必须是一个以空格分隔的标志，当 xargs 分析到含有 flag 这个标志的时候就停止。
- `-p` 当每次执行一个 argument 的时候询问一次用户。
- `-n` num 后面加次数，表示命令在执行的时候一次用的 argument 的个数，默认是用所有的。
- `-t` 表示先打印命令，然后再执行。
- `-i` 或者是-I，这得看 linux 支持了，将 xargs 的每项名称，一般是一行一行赋值给 {}，可以用 {} 代替。
- `-r` no-run-if-empty 当 xargs 的输入为空的时候则停止 xargs，不用再去执行了。
- `-s` num 命令行的最大字符数，指的是 xargs 后面那个命令的最大命令行字符数。
- `-L` num 从标准输入一次读取 num 行送给 command 命令。
- `-l` 同 -L。
- `-d` delim 分隔符，默认的 xargs 分隔符是回车，argument 的分隔符是空格，这里修改的是 xargs 的分隔符。
- `-x` exit 的意思，主要是配合-s 使用。。
- `-P` 修改最大的进程数，默认是 1，为 0 时候为 as many as it can ，这个例子我没有想到，应该平时都用不到的吧。
