---
layout:     post
title:      【One topic per day】Double Cola
subtitle:   前端题库，Javascript题集
date:       2019-03-26
author:     Jerry
header-img: img/post-bg-js-version.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# Double Cola

Sheldon, Leonard, Penny, Rajesh and Howard are in the queue for a "Double Cola" drink vending machine; there are no other people in the queue. The first one in the queue (Sheldon) buys a can, drinks it and doubles! The resulting two Sheldons go to the end of the queue. Then the next in the queue (Leonard) buys a can, drinks it and gets to the end of the queue as two Leonards, and so on.

For example, Penny drinks the third can of cola and the queue will look like this:
```
Rajesh, Howard, Sheldon, Sheldon, Leonard, Leonard, Penny, Penny
```
Write a program that will return the name of the person who will drink the n-th cola.

Input
The input data consist of an array which contains at least 1 name, and single integer n.

```
1  ≤  n  ≤  10000000000
```
### Output / Examples

Return the single line — the name of the person who drinks the n-th can of cola. The cans are numbered starting from 1.
```js
whoIsNext(["Sheldon", "Leonard", "Penny", "Rajesh", "Howard"], 1) == "Sheldon"
whoIsNext(["Sheldon", "Leonard", "Penny", "Rajesh", "Howard"], 52) == "Penny"
whoIsNext(["Sheldon", "Leonard", "Penny", "Rajesh", "Howard"], 7230702951) == "Leonard"
```

# reply
```js
//method 1:
function whoIsNext(names, r) {
  var l = names.length;
  while (r >= l) { r -= l; l *= 2; }
  return names[Math.ceil(names.length * r / l)-1];
}

//method 2:
function whoIsNext(names, r){
  if(r == 1){
    return "Sheldon"
  }
  var base = names.length;
  
  function getIndex(n, i) {
    i = i || base;
    if(n<i){
      return Math.floor(n * base / i);
    }
    return getIndex(n-i,i*2)
  }
  
  return names[getIndex(r-1)];
  
}

```



[同Github，欢迎star](https://github.com/xiqe/code-train/tree/master/javascript)
