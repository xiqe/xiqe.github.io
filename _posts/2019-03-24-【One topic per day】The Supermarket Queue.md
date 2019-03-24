---
layout:     post
title:      【One topic per day】The Supermarket Queue
subtitle:   前端题库，Javascript题集
date:       2019-03-24
author:     Jerry
header-img: img/post-bg-js-version.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# The Supermarket Queue

There is a queue for the self-checkout tills at the supermarket. Your task is write a function to calculate the total time required for all the customers to check out!

The function has two input variables:

- customers: an array (list in python) of positive integers representing the queue. Each integer represents a customer, and its value is the amount of time they require to check out.
- n: a positive integer, the number of checkout tills.
The function should return an integer, the total time required.

EDIT: A lot of people have been confused in the comments. To try to prevent any more confusion:

- There is only ONE queue, and
- The order of the queue NEVER changes, and
- Assume that the front person in the queue (i.e. the first element in the array/list) proceeds to a till as soon as it becomes free.
- The diagram on the wiki page I linked to at the bottom of the description may be useful.
So, for example:

```js
queueTime([5,3,4], 1)
// should return 12
// because when n=1, the total time is just the sum of the times

queueTime([10,2,3,3], 2)
// should return 10
// because here n=2 and the 2nd, 3rd, and 4th people in the 
// queue finish before the 1st person has finished.

queueTime([2,3,10], 2)
// should return 12
```

# Reply
```js
queueTime = (customers, n) => {
	let arr = new Array(n).fill(0);
    for(let i=0;i<customers.length;i++){
    	arr[arr.indexOf(Math.min.apply(null,arr))] += customers[i]
    }
    return Math.max.apply(null,arr)
}

```


[同Github，欢迎star](https://github.com/xiqe/code-train/blob/master/javascript/The%20Supermarket%20Queue.md)
