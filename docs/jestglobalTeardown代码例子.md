# Parent Node

- [ROOT](./root.md)
- [jest config globalTeardown](./jestconfigglobalTeardown.md)

# Child Node

# jest globalTeardown 代码例子

```js
const chalk = require("chalk");
const treeKill = require("tree-kill");
const { promisify } = require("util");
const path = require("path");
const rimraf = require("rimraf");
const os = require("os");

const DIR = path.join(os.tmpdir(), "jest_puppeteer_global_setup");

async function killProc(proc) {
  await promisify(treeKill)(proc.pid);
  console.log(chalk.green(`Successfully Close Page Server`));
}

module.exports = async function () {
  console.log(chalk.green("Teardown Page Server"));
  global.pageServerProc && killProc(global.pageServerProc);

  console.log(chalk.green("Teardown Puppeteer"));
  await global.__BROWSER__.close();
  rimraf.sync(DIR);
};
```
