# Parent Node

- [ROOT](./root.md)
- [jest config testEnvironment](./jestconfigtestEnvironment.md)

# Child Node

# jest testEnvironment puppeteer 代码例子

```js
const chalk = require("chalk");
const NodeEnvironment = require("jest-environment-node");
const puppeteer = require("puppeteer");
const fs = require("fs");
const path = require("path");
const os = require("os");

const DIR = path.join(os.tmpdir(), "jest_puppeteer_global_setup");

class PuppeteerEnvironment extends NodeEnvironment {
  constructor(config) {
    super(config);
  }

  async setup() {
    console.log(chalk.yellow("Setup Test Environment."));
    await super.setup();
    const wsEndpoint = fs.readFileSync(path.join(DIR, "wsEndpoint"), "utf8");
    if (!wsEndpoint) {
      throw new Error("wsEndpoint not found");
    }
    const browser = await puppeteer.connect({
      browserWSEndpoint: wsEndpoint,
    });
    this.global.__BROWSER__ = browser;
  }

  async teardown() {
    console.log(chalk.green("Teardown Test Environment."));
    await super.teardown();
  }

  runScript(script) {
    return super.runScript(script);
  }
}

module.exports = PuppeteerEnvironment;
```
