# jquery
```js
// 預設為get請求
$.ajax({
    url:"demo_test.txt",
    success:function(result){
        console.log(result);
    }
}
// 可透過method指定請求方式
$.ajax({
    url:"demo_test.txt",
    method:"POST",
    success:function(result){
	console.log(result);
    }
}
// 有参数，则增加data字段，有请求則增加headers字段，有錯誤處理則增加error字段
// 預設是按照表单提交post方法，data中虽然是json但是提交时轉換成表单
$.ajax({
    url:"demo_test.txt",
    data:{a:10},
    success:function(result){
    	console.log(result);
    },
    error:function(xhr,status,error){
    	console.log(error);
    }
});
// 傳輸json格式檔案，contentType改為application/json，並修改data格視為json
$.ajax({
    url:"demo_test.txt",
    headers:{ contentType: "application/json"},
    method:"POST",
    data:JSON.stringify({a:10}),
    success:function(result){
	console.log(result);
    }
});
```
# fetch
```js
// fetch基本用法
fetch(url,{
    headers:{
         'content-type': "application/x-www-form-urlencoded"
    },
    method:"POST",
    body:"a=12&b=33",
})
.then(res=>res.json())
.then(data=>console.log(res))
.catch(e=>{})
// fetch的post json用法
fetch(url,{
    headers:{
         'content-type': "application/json"
    },
    method:"POST",
    body:JSON.stringify({a:100}),
})
.then(res=>res.json())
.then(data=>console.log(res))
.catch(e=>{})
```
# axios
```js
// axios預設是json格式
axios({
    url:"http://localhost:99?x=1",
    method:"POST",
    data:{a:12}
})
.then(res=>console.log(res.data))
// 如果想改成form則需要修改headers和data格式
axios({
    url:"http://localhost:99?x=1",
    method:"POST",
    headers:{"Content-Type":"application/x-www-form-urlencoded"},
    data:"a=12&b=23"
})
.then(res=>console.log(res.data))

```
