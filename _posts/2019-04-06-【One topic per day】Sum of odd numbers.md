---
layout:     post
title:      【One topic per day】Sum of odd numbers
subtitle:   前端题库，Javascript题集
date:       2019-04-06
author:     Jerry
header-img: img/post-bg-js-version.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# Sum of odd numbers

Given the triangle of consecutive odd numbers:
```
             1
          3     5
       7     9    11
   13    15    17    19
21    23    25    27    29
...
```
Calculate the row sums of this triangle from the row index (starting at index 1) e.g.:
```js
rowSumOddNumbers(1); // 1
rowSumOddNumbers(2); // 3 + 5 = 8
```

# reply
```js
//method 1:
function rowSumOddNumbers(n) {
  return Math.pow(n, 3);
}

//method 2:
function rowSumOddNumbers(n) {
  let index = (n-1)*n/2,sum=0;
  for(let i=1;i<=n;i++){
    sum += 2*(index+i) - 1
  }
  return sum;
}
```

[同Github，欢迎star](https://github.com/xiqe/code-train/issues)
