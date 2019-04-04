---
layout:     post
title:      【One topic per day】Basic Nico variation
subtitle:   前端题库，Javascript题集
date:       2019-04-05
author:     Jerry
header-img: img/post-bg-js-version.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# Basic Nico variation
Write a function nico/nico() that accepts two parameters:

key/$key - string consists of unique letters and digits
message/$message - string to encode
and encodes the message using the key.

First create a numeric key basing on a provided key by assigning each letter position in which it is located after setting the letters from key in an alphabetical order.

For example, for the key crazy we will get 23154 because of acryz (sorted letters from the key).
Let's encode secretinformation using our crazy key.
```
2 3 1 5 4
---------
s e c r e
t i n f o
r m a t i
o n
```
After using the key:
```
1 2 3 4 5
---------
c s e e r
n t i o f
a r m i t
  o n   
```
### Notes
The message is never shorter than the key.

### Examples
```js
nico("crazy", "secretinformation") => "cseerntiofarmit on  "
nico("abc", "abcd") => "abcd  "
nico("ba", "1234567890") => "2143658709" 
nico("key", "key") => "eky" 
```
Check the test cases for more samples.

### Collection
Basic DeNico - if you like this kata , try to decode the message in the next kata

# reply
```js
function nico  (key, message)  {
  var eky = key.split``.sort(),
      ekyL = eky.length,
      groups = message.length/key.length,
      nicoMess = ''
  for (var group = 0; group < groups; group++){
    for (var i = 0; i<ekyL; i++){
      nicoMess += message[key.indexOf(eky[i])+group*ekyL] || ' '
    }
  }
  return nicoMess
}
```


[同Github，欢迎star](https://github.com/xiqe/code-train/issues)
