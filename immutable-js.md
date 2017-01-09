---
title: Immutable.js
category: JavaScript libraries
layout: default-ad
---

```js
var Immutable = require('immutable')
```

## Maps

```js
var map = Immutable.Map({ a: 1, b: 2, c: 3 })

var mapped = map
  .set('b', 50)
  .get('b')

mapped === 50 // true
```

## Lists

```js
var list = Immutable.List.of(1, 2)
var list2 = Immutable.List.of(6, 7)
var list3 = Immutable.List.of(8, 9)

var workingList = list
  .push(3, 4, 5)
  .unshift(10)
  .concat(list2, list3)

workingList.get(0) === 10 // true
workingList.size === 10 // true
```

## Nested maps

```js
var nested = Immutable.fromJS({ user: { profile: { name: 'John' } } })

var result = nested
  .mergeDeep({ user: { profile: { age: 90 } } })
  .setIn([ 'user', 'profile', 'name' ], 'Jack')
  .updateIn([ 'user', 'profile', 'name' ], (s) => s.toUpperCase())
  .getIn(['user', 'profile', 'name'])

result === 'JACK' // true
```

