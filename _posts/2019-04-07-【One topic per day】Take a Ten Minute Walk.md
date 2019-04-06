---
layout:     post
title:      【One topic per day】Take a Ten Minute Walk
subtitle:   前端题库，Javascript题集
date:       2019-04-07
author:     Jerry
header-img: img/post-bg-js-version.jpg
catalog: true
tags:
    - 面试题
    - Javascript
    - 前端题库
    - One topic per day
---

# Take a Ten Minute Walk
You live in the city of Cartesia where all roads are laid out in a perfect grid. You arrived ten minutes too early to an appointment, so you decided to take the opportunity to go for a short walk. The city provides its citizens with a Walk Generating App on their phones -- everytime you press the button it sends you an array of one-letter strings representing directions to walk (eg. ['n', 's', 'w', 'e']). You always walk only a single block in a direction and you know it takes you one minute to traverse one city block, so create a function that will return true if the walk the app gives you will take you exactly ten minutes (you don't want to be early or late!) and will, of course, return you to your starting point. Return false otherwise.
```
Note: you will always receive a valid array containing a random assortment of direction letters ('n', 's', 'e', or 'w' only). It will never give you an empty array (that's not a walk, that's standing still!).
```

### Example
```
isValidWalk(['n','s','n','s','n','s','n','s','n','s']), 'should return true'
isValidWalk(['w','e','w','e','w','e','w','e','w','e','w','e']), 'should return false'
isValidWalk(['w']), 'should return false'
!isValidWalk(['n','n','n','s','n','s','n','s','n','s']), 'should return false'
```
# reply
```js
function isValidWalk(walk) {
  if(walk.length!==10) return false;
  let obj={};
  for(let i=0;i<walk.length;i++){
    obj[walk[i]]?obj[walk[i]]++:obj[walk[i]]=1
  }
  return (obj['n']==obj['s']&&obj['e']==obj['w'])?true:false
}
```

[同Github，欢迎star](https://github.com/xiqe/code-train/issues)
