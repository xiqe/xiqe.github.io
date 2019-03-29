---
layout:     post
title:      【One topic per day】Exes and Ohs
subtitle:   前端题库，Javascript题集
date:       2019-03-29
author:     Jerry
header-img: img/post-bg-js-version.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# Exes and Ohs

Check to see if a string has the same amount of 'x's and 'o's. The method must return a boolean and be case insensitive. The string can contain any char.

Examples input/output:

```js
XO("ooxx") => true
XO("xooxx") => false
XO("ooxXm") => true
XO("zpzpzpp") => true // when no 'x' and 'o' is present should return true
XO("zzoo") => false
```

# Reply
```js
//method 1：
XO = str => {
    return str.toLowerCase().split('x').length == str.toLowerCase().split('o').length
}

//method 2：
XO = str => {
    let x = str.match(/x/gi);
    let o = str.match(/o/gi);
    return (x && x.length) === (o && o.length);
}
```



[同Github，欢迎star](https://github.com/xiqe/code-train/tree/master/javascript)
