---
layout:     post
title:      【One topic per day】Disemvowel Trolls
subtitle:   前端题库，Javascript题集
date:       2019-04-11
author:     Jerry
header-img: img/post-bg-js-version.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# Disemvowel Trolls
Trolls are attacking your comment section!

A common way to deal with this situation is to remove all of the vowels from the trolls' comments, neutralizing the threat.

Your task is to write a function that takes a string and return a new string with all vowels removed.

For example, the string "This website is for losers LOL!" would become "Ths wbst s fr lsrs LL!".

Note: for this kata y isn't considered a vowel.

# reply
```js
function disemvowel(str) {
  let vaild = ['a','e','i','o','u'];
  return str.split('').reduce((s,x)=>{
    return s += (vaild.includes(x.toLowerCase()))?'':x
  },'');
}
```


[同Github，欢迎star](https://github.com/xiqe/code-train/issues)
