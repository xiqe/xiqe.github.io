---
layout:     post
title:      【One topic per day】Sum of two lowest positive integers
subtitle:   前端题库，Javascript题集
date:       2019-04-02
author:     Jerry
header-img: img/post-bg-js-version.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# Sum of two lowest positive integers
Create a function that returns the sum of the two lowest positive numbers given an array of minimum 4 integers. No floats or empty arrays will be passed.

For example, when an array is passed like `[19, 5, 42, 2, 77]`, the output should be `7`.

`[10, 343445353, 3453445, 3453545353453]` should return `3453455`.

# reply
```js
function sumTwoSmallestNumbers(numbers) {  
  var [ a, b ] = numbers.sort((a, b) => a - b)
  return a + b
}
```



[同Github，欢迎star](https://github.com/xiqe/code-train/issues)
