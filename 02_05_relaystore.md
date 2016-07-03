# RelayStore

* RelayStore
  * Client-side cache
  * Normalized flattened graph representation
    * No redundancy
  * 3 layers
    * Queued data `_queuedRecords`
    * Store data `_records`
    * Cached data `_cachedRecords`

<!--
* `__dataID__`
* hoist levels and create links link
* deleting is setting null
-->
```js
_rootCallMap: {
  user: {
    'VXNlcjox': 'VXNlcjox',
  },
},
_records: {
  'VXNlcjox': {
    __dataID__: 'VXNlcjox',
    __typename: 'User',
    id: 'VXNlcjox',
    name: 'Viacheslav',
    avatar: {
      __dataID__: 'client:1',
    },
    posts: {
      __dataID__: 'client:2',
    },
  },
  'client:1': {
    __dataID__: 'client:1',
    __typename: 'Avatar',
    avatarUrl: 'http://avatar/vslinko.png',
  },
  'client:2': {
    __dataID__: 'client:2',
    __typename: null,
    __filterCalls__: [],
    __range__: {/* GraphQLRange */},
  },
  'client:client:2:UG9zdDox': {
    __dataID__: 'client:client:2:UG9zdDox',
    cursor: 'YXJyYXljb25uZWN0aW9uOjA=',
    node: {
      __dataID__: 'UG9zdDox',
    },
  },
  'UG9zdDox': {
    __dataID__: 'UG9zdDox',
    __typename: 'Post',
    title: 'Relay Internals'
  },
},
```

* GraphQLRange
  * ES2015 class
  * Smartest part of the store

<!--
* Cursors
* Get first 5 after this cursor
* 10 -> 20 = 10
* `__filterCalls__`
-->
