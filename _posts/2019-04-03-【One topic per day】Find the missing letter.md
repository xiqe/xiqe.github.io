---
layout:     post
title:      【One topic per day】Find the missing letter
subtitle:   前端题库，Javascript题集
date:       2019-04-03
author:     Jerry
header-img: img/post-bg-js-version.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# Find the missing letter

Write a method that takes an array of consecutive (increasing) letters as input and that returns the missing letter in the array.

You will always get an valid array. And it will be always exactly one letter be missing. The length of the array will always be at least 2.
The array will always contain letters in only one case.

### Example:
```
['a','b','c','d','f'] -> 'e'
['O','Q','R','S'] -> 'P'
```
(Use the English alphabet with 26 letters!)

Have fun coding it and please don't forget to vote and rank this kata! :-)

I have also created other katas. Take a look if you enjoyed this kata!

# reply
```js
//method 1:
function findMissingLetter(array){
   var i=array[0].charCodeAt();
   array.map(x=>  x.charCodeAt()==i?i++:i);
   return String.fromCharCode(i);
}

//method 2:
function findMissingLetter(array){
  const vaild = 'abcdefghijklmnopqrstuvwxyz';
  let [a,b] = [vaild.indexOf(array[0].toLowerCase()),vaild.indexOf(array[array.length-1].toLowerCase())];
  for(let i=0;i<array.length;i++){
    if(array[i].toLowerCase() !== vaild[a+i]) return (/[a-z]/.test(array[i]))?vaild[a+i]:vaild[a+i].toUpperCase()
  }
}
```



[同Github，欢迎star](https://github.com/xiqe/code-train/issues)
