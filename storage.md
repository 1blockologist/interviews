## Storage Wrapper

You have an object lowLevelStorage with the following interface:

```js
get(key, callback)
put(key, value, callback)
del(key, callback)
```

You hate callbacks, and want to write a wrapper that exports a promise-based interface, as well as an additional higher level function `batchPut`. The sample usage looks like this:

```js
const highLevelStorage = wrap(lowLevelStorage)
highLevelStorage.put('a ', 1) // returns a Promise
highLevelStorage.get('a')     // returns a Promise
highLevelStorage.del('a')     // returns a Promise
highLevelStorage.batchPut([   // returns a Promise
  { key: 'a', value: 1 },
  { key: 'b', value: 2 },
])
```

Implement the `wrap` function above. If you're feeling ambitious, write a lowLevelStorage mock, and test your implementation.