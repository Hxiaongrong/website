---
title: 手写new
date: 2021-01-05 15:17:39
tags: 手写系列
cover:
---
```
function _new(func, ...args) {
    if(typeof func !== 'function') throw TypeError(func + ' is not a constructor')
    const obj = Object.create(func.prototype)
    const result = func.apply(obj, args)
    if(typeof result === 'object') return result
    return obj
}

```