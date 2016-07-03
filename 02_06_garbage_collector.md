# Garbage Collector

* Removing unused data from the store
* Using simple counters

```js
class RelayGarbageCollector {
  incrementReferenceCount(dataID: DataID): void {}

  decrementReferenceCount(dataID: DataID): void {}

  acquireHold(): GarbageCollectionHold {}

  collectFromNode(dataID: DataID): void {}

  collect(): void {}
}
```
