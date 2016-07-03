# Schedulers

```js
Relay.injectTaskScheduler((task) => {
  window.requestIdleCallback(() => task())
})
```

<!--
* TaskScheduler
* GarbageScheduler
* requestIdleCallback
-->
