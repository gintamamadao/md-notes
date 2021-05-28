# Parent Node

- [root](./root.md)
- [ECMAScript 学习杂记](./ECMAScript学习杂记.md)

# Child Node

# Detail

- 注册
  - 加入到相关事件的关联队列中
  - 返回退订的句柄
- 派发
  - 触发某个事件的所有函数
- 退订
  - 清空事件或者将某个事件从队列中删除

```js
class Message {
  on(event, fn) {
    if (!event || typeof fn !== "function") {
      return;
    }
    const eventsMap = this.eventsMap || {};
    const fnList = eventsMap[event] || [];
    fnList.push(fn);
    eventsMap[event] = fnList;
    this.eventsMap = eventsMap;
    const _this = this;
    return function () {
      _this.off(event, fn);
    };
  }

  emit(event, ...arg) {
    if (!event) {
      return;
    }
    const eventsMap = this.eventsMap || {};
    const fnList = eventsMap[event] || [];
    fnList.forEach((fn) => fn.apply(null, arg));
  }

  off(event, fn) {
    if (!event) {
      return;
    }
    const eventsMap = this.eventsMap || {};
    let fnList = eventsMap[event] || [];
    if (typeof fn !== "function") {
      eventsMap[event] = [];
    } else {
      fnList = fnList.filter((eventFn) => {
        return eventFn !== fn;
      });
      eventsMap[event] = fnList;
    }
  }
}
```
