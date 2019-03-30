---
layout:     post
title:      【One topic per day】Bit Counting
subtitle:   前端题库，Javascript题集
date:       2019-03-31
author:     Jerry
header-img: img/post-bg-js-version.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# Bit Counting

Write a function that takes an integer as input, and returns the number of bits that are equal to one in the binary representation of that number. You can guarantee that input is non-negative.

Example: The binary representation of `1234` is `10011010010`, so the function should return `5` in this case

# reply
```js
countBits = (n) => {n.toString(2).split('0').join('').length}
```





[同Github，欢迎star](https://github.com/xiqe/code-train/tree/master/javascript)
