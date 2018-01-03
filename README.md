# question

> 记录一些面试题，了解自己的不足。

## 2018 

1. 学会使用vue并有实际开发项目（vue + vuex + vue-router + axios）.
2. 尽量使用Eslint.
3. 代码要规范~规范~规范~.
4. 了解常用的ES6.
5. npm上发布一个包（可以是vue插件，也可以是Jquery插件）.
7. github上的组织里面想一个要公共开发的插件，定个题目就行.
8. 整理下自己的技能树（写在IO上）.
9. 简单看下jquery一个模块的源码.
10. 工作态度上：快快乐乐上班，情绪要正能量满满，不因工作繁重而抱怨，也不因不过不饱和而浑浑噩噩.
11. 多看点书，少打游戏（至少每天看30分钟）.

----

### 1 下面代码输出的结果是?

```js
var tasks = [];
var output = function(i){
  return new Promise(function(resolve){
   setTimeout(function(){
      console.log(new Date(), i)
      resolve(i);
    },1000)
  })
}

for(var i = 0; i < 5; i ++){
  tasks.push(output(i));
}

Promise.all(tasks).then(function(i){
  setTimeout(function(){
    console.log(new Date(), i)
  },1000)
})
```

### 2 下面代码输出的结果是？

```js
for(var i = 0; i < 5; i++){
  setTimeout(function(){
    console.log(new Date(), i)
  }, 1000 * i)
}

console.log(new Date(), i)
```

### 3 前端性能优化？

### 4 前端与后端交互的时候，如何实现数据加密？

### 5 前端与IOS,Android的混合开发中的交互？

