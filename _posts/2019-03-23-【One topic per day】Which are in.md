---
layout:     post
title:      【One topic per day】Which are in？
subtitle:   前端题库，Javascript题集
date:       2019-01-30
author:     Jerry
header-img: img/post-bg-css3.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# Which are in?

Given two arrays of strings `a1` and `a2` return a sorted array r in lexicographical order of the strings of a1 which are substrings of strings of a2.

#Example 1: 

a1 = ["arp", "live", "strong"]

a2 = ["lively", "alive", "harp", "sharp", "armstrong"]

returns ["arp", "live", "strong"]

#Example 2: 

a1 = ["tarp", "mice", "bull"]

a2 = ["lively", "alive", "harp", "sharp", "armstrong"]

returns []

### Notes:
- Arrays are written in "general" notation. See "Your Test Cases" for examples in your language.

- In Shell bash a1 and a2 are strings. The return is a string where words are separated by commas.

- Beware: r must be without duplicates.
- Don't mutate the inputs.

## Reply
```js
//method 1:
inArray = (a1, a2) => {
  var str = a2.join(' ');
  return a1.filter(s => str.indexOf(s) !== -1).sort();
}

//method 2:
inArray = (a1, a2) => {
  return array1
    .filter(a1 => array2.find(a2 => a2.match(a1)))
    .sort()
}

```

[同Github，欢迎star](https://github.com/xiqe/code-train/blob/master/javascript/Which%20are%20in.md)
