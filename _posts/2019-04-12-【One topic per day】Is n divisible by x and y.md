---
layout:     post
title:      【One topic per day】Is n divisible by x and y?
subtitle:   前端题库，Javascript题集
date:       2019-04-12
author:     Jerry
header-img: img/post-bg-js-version.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# Is n divisible by x and y?
Create a function isDivisible(n, x, y) that checks if a number n is divisible by two numbers x AND y. All inputs are positive, non-zero digits.
```
Example:
isDivisible(3,1,3)--> true because 3 is divisible by 1 and 3
isDivisible(12,2,6)--> true because 12 is divisible by 2 and 6
isDivisible(100,5,3)--> false because 100 is not divisible by 3
isDivisible(12,7,5)--> false because 12 is neither divisible by 7 nor 5
```

# reply
```js
function isDivisible(n, x, y) {
  return n % x === 0 && n % y === 0
}
```


[同Github，欢迎star](https://github.com/xiqe/code-train/issues)
