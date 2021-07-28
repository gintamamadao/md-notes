# Parent Node

- [ROOT](./root.md)
- [liftoff](./liftoff.md)

# Child Node

- [liftoff config name](./liftoffconfigname.md)
- [liftoff config moduleName](./liftoffconfigmoduleName.md)
- [liftoff config configName](./liftoffconfigconfigName.md)

# Liftoff 配置

```js
const Hacker = new Liftoff({
  name: "hacker",
  processTitle: "hacker",
  moduleName: "hacker",
  configName: "hackerfile",
  extensions: {
    ".js": null,
    ".json": null,
    ".coffee": "coffee-script/register",
  },
  v8flags: ["--harmony"], // or v8flags: require('v8flags')
});
```
