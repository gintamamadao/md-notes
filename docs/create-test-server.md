# Parent Node

- [ROOT](./root.md)
- [ECMAScript 插件依赖](./ECMAScript插件依赖.md)

# Child Node

# create-test-server

- 可以建立一个简单的服务器作为测试用

```js
const writeData = (data, res) => {
  res.setHeader('access-control-allow-origin', '*');
  res.send(data);
};

  let server;
  beforeAll(async () => {
    server = await createTestServer();
  });
  afterAll(() => {
    server.close();
  });

  const prefix = api => `${server.url}${api}`;

  // 测试请求
  describe('test valid fetch', () => {
    it('response should be true', async done => {
      server.get('/test/fetch', (req, res) => {
        setTimeout(() => {
          writeData('ok', res);
        }, 1000);
      });

      let response = await fetch(prefix('/test/fetch'));
      expect(response.ok).toBe(true);
      done();
    });
  }
```
