---
layout:     post
title:      【One topic per day】IQ Test
subtitle:   前端题库，Javascript题集
date:       2019-04-01
author:     Jerry
header-img: img/post-bg-js-version.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# IQ Test

Bob is preparing to pass IQ test. The most frequent task in this test is to find out which one of the given numbers differs from the others. Bob observed that one number usually differs from the others in evenness. Help Bob — to check his answers, he needs a program that among the given numbers finds one that is different in evenness, and return a position of this number.

`!` Keep in mind that your task is to help Bob solve a real IQ test, which means indexes of the elements start from `1 (not 0)`

##Examples :
```js
iqTest("2 4 7 8 10") => 3 // Third number is odd, while the rest of the numbers are even
iqTest("1 2 1 1") => 2 // Second number is even, while the rest of the numbers are odd
```

# reply
```js
//method 1:
function iqTest(numbers){
  var odd = numbers.filter(function(el){ return el % 2 === 1});
  var even = numbers.filter(function(el){ return el % 2 === 0});
  return odd.length < even.length ? (numbers.indexOf(odd[0]) + 1) : (numbers.indexOf(even[0]) + 1);
}

//method 2:
function iqTest(numbers){
  let [evens,odds,numbers] = [[],[], numbers.split(' ')];
  for (var i = 0; i < numbers.length; i++) {
    if (numbers[i] & 1) {    //位运算，二进制奇数为1，也可以%2==0来判断
      odds.push(i + 1)
    } else {
      evens.push(i + 1)
    }
  }
  return evens.length == 1 ? evens[0] : odds[0]
}
```



[同Github，欢迎star](https://github.com/xiqe/code-train/issues)
