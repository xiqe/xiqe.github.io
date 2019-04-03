---
layout:     post
title:      【One topic per day】Persistent Bugger
subtitle:   前端题库，Javascript题集
date:       2019-04-04
author:     Jerry
header-img: img/post-bg-js-version.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# Persistent Bugger.
Write a function, persistence, that takes in a positive parameter num and returns its multiplicative persistence, which is the number of times you must multiply the digits in num until you reach a single digit.

### For example:
```js
 persistence(39) === 3 // because 3*9 = 27, 2*7 = 14, 1*4=4
                       // and 4 has only one digit

 persistence(999) === 4 // because 9*9*9 = 729, 7*2*9 = 126,
                        // 1*2*6 = 12, and finally 1*2 = 2

 persistence(4) === 0 // because 4 is already a one-digit number
```
# reply
```js
function persistence(num) {
  return count(num,0);
  function count(num,sum){
    return (String(num).length>1)?count(String(num).split('').reduce((s,x)=>{return s=s*x},1),++sum):sum;
  }
}
```


[同Github，欢迎star](https://github.com/xiqe/code-train/issues)
