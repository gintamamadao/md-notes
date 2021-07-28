# Parent Node

- [ROOT](./root.md)
- [Liftoff api](./Liftoffapi.md)

# Child Node

# Liftoff execute

```js
execute(env, [forcedFlags], callback(env, argv));
```

```js
const Liftoff = require("liftoff");
const MyApp = new Liftoff({ name: "myapp" });
const onExecute = function (env, argv) {
  // Do post-execute things
  console.log("my environment is:", env);
  console.log("my cli options are:", argv);
  console.log("my liftoff config is:", this);
};
const onPrepare = function (env) {
  var forcedFlags = ["--trace-deprecation"];
  MyApp.execute(env, forcedFlags, onExecute);
};
MyApp.prepare({}, onPrepare);
```
