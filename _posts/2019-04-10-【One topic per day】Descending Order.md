---
layout:     post
title:      【One topic per day】Descending Order
subtitle:   前端题库，Javascript题集
date:       2019-04-10
author:     Jerry
header-img: img/post-bg-js-version.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# Descending Order
our task is to make a function that can take any non-negative integer as a argument and return it with its digits in descending order. Essentially, rearrange the digits to create the highest possible number.

### Examples:
Input: `21445` Output: `54421`

Input: `145263` Output: `654321`

Input: `1254859723` Output: `9875543221`

# reply
```js
function descendingOrder(n){
  return Number(String(n).split("").sort((a,b)=>b-a).join(""));
}
```


[同Github，欢迎star](https://github.com/xiqe/code-train/issues)
