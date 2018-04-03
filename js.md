## JAVASCRIPT

### 1 - 下面代码输出的结果是?

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

### 2 - 下面代码输出的结果是？

```js
for(var i = 0; i < 5; i++){
  setTimeout(function(){
    console.log(new Date(), i)
  }, 1000 * i)
}

console.log(new Date(), i)
```

### 3 - 前端性能优化？

### 4 - 前端与后端交互的时候，如何实现数据加密？

### 5 - 前端与IOS,Android的混合开发中的交互？

### 6 - 创建原生的ajax请求？
```js
 1    ajax({
 2         url: "./TestXHR.aspx",              //请求地址
 3         type: "POST",                       //请求方式
 4         data: { name: "super", age: 20 },        //请求参数
 5         dataType: "json",
 6         success: function (response, xml) {
 7             // 此处放成功后执行的代码
 8         },
 9         fail: function (status) {
10             // 此处放失败后执行的代码
11         }
12     });
13
14     function ajax(options) {
15         options = options || {};
16         options.type = (options.type || "GET").toUpperCase();
17         options.dataType = options.dataType || "json";
18         var params = formatParams(options.data);
19
20         //创建 - 非IE6 - 第一步
21         if (window.XMLHttpRequest) {
22             var xhr = new XMLHttpRequest();
23         } else { //IE6及其以下版本浏览器
24             var xhr = new ActiveXObject('Microsoft.XMLHTTP');
25         }
26
27         //接收 - 第三步
28         xhr.onreadystatechange = function () {
29             if (xhr.readyState == 4) {
30                 var status = xhr.status;
31                 if (status >= 200 && status < 300) {
32                     options.success && options.success(xhr.responseText, xhr.responseXML);
33                 } else {
34                     options.fail && options.fail(status);
35                 }
36             }
37         }
38
39         //连接 和 发送 - 第二步
40         if (options.type == "GET") {
41             xhr.open("GET", options.url + "?" + params, true);
42             xhr.send(null);
43         } else if (options.type == "POST") {
44             xhr.open("POST", options.url, true);
45             //设置表单提交时的内容类型
46             xhr.setRequestHeader("Content-Type", "application/x-www-form-urlencoded");
47             xhr.send(params);
48         }
49     }
50     //格式化参数
51     function formatParams(data) {
52         var arr = [];
53         for (var name in data) {
54             arr.push(encodeURIComponent(name) + "=" + encodeURIComponent(data[name]));
55         }
56         arr.push(("v=" + Math.random()).replace("."));
57         return arr.join("&");
58     }
```

### 7 - `<div name="abc" abc="1"></div>` 如何获取其中的 `abc` 属性？
```js
// jq
$('[name="abc"]').attr('abc');

// js
var a = document.getElementByName('abc');
a.getAttribute('abc');
```

### 8 - 什么是MVVM，简单解释下？

### 9 - 如何实现数组去重？

### 10 - 如何实现浅复制和深复制？

```js
var cloneObj = function(obj){
    var str, newobj = obj.constructor === Array ? [] : {};
    if(typeof obj !== 'object'){
        return;
    } else if(window.JSON){
        str = JSON.stringify(obj), //系列化对象
        newobj = JSON.parse(str); //还原
    } else {
        for(var i in obj){
            newobj[i] = typeof obj[i] === 'object' ?
            cloneObj(obj[i]) : obj[i];
        }
    }
    return newobj;
};
```

### 11 - 如何实现菲波那切数列？

### 12 - 知道哪些排序的方法？大致的实现思路？