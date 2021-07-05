# Parent Node

- [ROOT](./root.md)
- [jest 学习杂记](./jest学习杂记.md)

# Child Node

# jest 和 jsdom 配合使用

```js
const NodeEnvironment = require("jest-environment-node");
const { JSDOM, VirtualConsole } = require("jsdom");

class JestEnv extends NodeEnvironment {
  constructor(config, options) {
    super(config);
    this.dom = new JSDOM("<!DOCTYPE html>", {
      pretendToBeVisual: true,
      runScripts: "dangerously",
      url: config.testURL,
      virtualConsole: new VirtualConsole().sendTo(options.console || console),
      ...config.testEnvironmentOptions,
    });
    this.global._JSDOM = this.dom;
    this.global.window = this.dom.window;
  }
  async setup() {
    await super.setup();
  }
  async teardown() {
    await super.teardown();
  }

  runScript(script) {
    return super.runScript(script);
  }
}

module.exports = JestEnv;
```
