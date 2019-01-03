### window.postMessage

示例

```typescript
(document.getElementById("circuit_iframe") as HTMLIFrameElement).contentWindow.postMessage(data, "*");
```

- window.postMessage() 方法可以安全地实现跨源通信
- 向目标窗口发送MessageEvent消息
- ```otherWindow.postMessage(message, targetOrigin, [transfer]);```
- message: 将要发送到其他 window的数据。它将会被结构化克隆算法序列化。这意味着你可以不受什么限制的将数据对象安全的传送给目标窗口而无需自己序列化。
- targetOrigin: 如果你明确的知道消息应该发送到哪个窗口，那么请始终提供一个有确切值的targetOrigin，而不是*。不提供确切的目标将导致数据泄露到任何对数据感兴趣的恶意站点。