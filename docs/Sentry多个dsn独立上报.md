# Parent Node

- [ROOT](./root.md)
- [Sentry 学习杂记](./Sentry学习杂记.md)

# Child Node

# Sentry 多个 dsn 独立上报

```js
import * as Sentry from "@sentry/browser";

// Very happy integration that'll prepend and append very happy stick figure to the message
class HappyIntegration {
  constructor() {
    this.name = "HappyIntegration";
  }

  setupOnce() {
    Sentry.addGlobalEventProcessor((event) => {
      const self = Sentry.getCurrentHub().getIntegration(HappyIntegration);
      // Run the integration ONLY when it was installed on the current Hub
      if (self) {
        event.message = `\\o/ ${event.message} \\o/`;
      }
      return event;
    });
  }
}

HappyIntegration.id = "HappyIntegration";

const client1 = new Sentry.BrowserClient({
  dsn: "https://123@sentry.io/123",
  integrations: [...Sentry.defaultIntegrations, new HappyIntegration()],
  beforeSend(event) {
    console.log("client 1", event);
    return null; // Returning null does not send the event
  },
});
const hub1 = new Sentry.Hub(client1);

const client2 = new Sentry.BrowserClient({
  dsn: "https://123@sentry.io/456",
  integrations: [...Sentry.defaultIntegrations, new HappyIntegration()],
  beforeSend(event) {
    console.log("client 2", event);
    return null; // Returning null does not send the event
  },
});
const hub2 = new Sentry.Hub(client2);

hub1.run((currentHub) => {
  currentHub.captureMessage("a");
  currentHub.configureScope((scope) => {
    scope.setTag("a", "b");
  });
});

hub2.run((currentHub) => {
  currentHub.captureMessage("x");
  currentHub.configureScope((scope) => {
    scope.setTag("c", "d");
  });
});

// throw new Error("My Error");
```

- 如果用的是 @sentry/react-native，就调用 Sentry.ReactNativeClient.
