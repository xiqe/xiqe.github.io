---
layout:     post
title:      【One topic per day】Isograms
subtitle:   前端题库，Javascript题集
date:       2019-04-09
author:     Jerry
header-img: img/post-bg-js-version.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# Isograms

An isogram is a word that has no repeating letters, consecutive or non-consecutive. Implement a function that determines whether a string that contains only letters is an isogram. Assume the empty string is an isogram. Ignore letter case.

```js
isIsogram( "Dermatoglyphics" ) == true
isIsogram( "aba" ) == false
isIsogram( "moOse" ) == false // -- ignore letter case
```

# reply
```js
function isIsogram(str){
  return new Set(str.toUpperCase()).size == str.length;
}
```


[同Github，欢迎star](https://github.com/xiqe/code-train/issues)
