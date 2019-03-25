---
layout:     post
title:      【One topic per day】Sum of the first nth term of Series
subtitle:   前端题库，Javascript题集
date:       2019-03-25
author:     Jerry
header-img: img/post-bg-js-version.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# Sum of the first nth term of Series

Task: Your task is to write a function which returns the sum of following series upto nth term(parameter).
```
Series: 1 + 1/4 + 1/7 + 1/10 + 1/13 + 1/16 +...
```
Rules:
- You need to round the answer to 2 decimal places and return it as String.
- If the given value is 0 then it should return 0.00
- You will only be given Natural Numbers as arguments.
Examples:
```
SeriesSum(1) => 1 = "1.00"
SeriesSum(2) => 1 + 1/4 = "1.25"
SeriesSum(5) => 1 + 1/4 + 1/7 + 1/10 + 1/13 = "1.57"
```

# Reply
```js
SeriesSum = num => {
    let sum = 0;
    for(let i=0;i<num;i++)sum += 1/(i*3 + 1);
    return sum.toFixed(2);
}
```



[同Github，欢迎star](https://github.com/xiqe/code-train/blob/master/javascript/Sum%20of%20the%20first%20nth%20term%20of%20Series.md)
