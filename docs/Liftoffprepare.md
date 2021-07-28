# Parent Node

- [ROOT](./root.md)
- [Liftoff api](./Liftoffapi.md)

# Child Node

# Liftoff prepare

```js
MyApp.prepare(
  {
    cwd: argv.cwd,
    configPath: argv.myappfile,
    require: argv.require,
    completion: argv.completion,
  },
  onPrepare
);
```

- prepare 完成的回调函数会传入参数 env， 有以下属性
  - cwd：当前工作目录
  - require：提起尝试预加载的模块数组
  - configNameSearch：搜索的配置文件
  - configPath：配置文件的完整路径（如果找到）
  - configBase：配置文件的基本目录（如果找到）
  - modulePath：项目所依赖的本地模块的完整路径（如果找到）
  - modulePackage：本地模块的 package.json 的内容（如果找到）
  - configFiles：每个找到的配置文件的文件路径对象（如果找不到，则文件路径值将为 null）
