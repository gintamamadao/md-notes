# Parent Node

- [ROOT](./root.md)
- [glob](./glob.md)

# Child Node

# glob 匹配规则

- `*` 匹配单个路径部分中的 0 个或多个字符
- `?` 匹配 1 个字符
- `[...]`匹配一系列字符，类似于 RegExp 范围。如果范围的第一个字符是!或，^则它匹配不在范围内的任何字符。
- `!(pattern|pattern|pattern)` 匹配与提供的任何模式都不匹配的任何内容。
- `?(pattern|pattern|pattern)` 匹配提供的模式的零次或一次出现。
- `+(pattern|pattern|pattern)` 匹配所提供模式的一次或多次出现。
- `*(a|b|c)` 匹配提供的模式的零次或多次出现
- `@(pattern|pat*|pat?erN)` 与提供的模式之一完全匹配
- `**` 如果“globstar”在路径部分中单独存在，则它匹配零个或多个目录和子目录以搜索匹配项。它不会抓取符号链接的目录。
