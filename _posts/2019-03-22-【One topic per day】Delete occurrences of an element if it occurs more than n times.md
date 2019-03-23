---
layout:     post
title:      【One topic per day】Delete occurrences of an element if it occurs more than n times？
subtitle:   前端题库，Javascript题集
date:       2019-03-22
author:     Jerry
header-img: img/post-bg-js-version.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# Delete occurrences of an element if it occurs more than n times

### Enough is enough!
Alice and Bob were on a holiday. Both of them took many pictures of the places they've been, and now they want to show Charlie their entire collection. However, Charlie doesn't like this sessions, since the motive usually repeats. He isn't fond of seeing the Eiffel tower 40 times. He tells them that he will only sit during the session if they show the same motive at most N times. Luckily, Alice and Bob are able to encode the motive as a number. Can you help them to remove numbers such that their list contains each number only up to N times, without changing the order?

### Task
Given a list lst and a number N, create a new list that contains each number of lst at most N times without reordering. For example if N = 2, and the input is [1,2,3,1,2,1,2,3], you take [1,2,3,1,2], drop the next [1,2] since this would lead to 1 and 2 being in the result 3 times, and then take 3, which leads to [1,2,3,1,2,3].

### Example
```js
deleteNth ([1,1,1,1],2) // return [1,1]

deleteNth ([20,37,20,21],1) // return [20,37,21]
```

# Reply
```js
deleteNth = (arr,n) => {
  let obj = {};
  return arr.filter(x=>{
    (obj[x])?obj[x]++:obj[x] = 1;
    return obj[x]<=n
  })
}

```


[同Github，欢迎star](https://github.com/xiqe/code-train/blob/master/javascript/Delete%20occurrences%20of%20an%20element%20if%20it%20occurs%20more%20than%20n%20times.md)
