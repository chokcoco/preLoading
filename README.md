# preLoading -- 预加载
页面的预加载方案，各类预加载方法示例。

## 使用 window.onload 事件
将 loading page 写在一个 div 块中，并放在 body 内容的最前面，这样 loading page 将最先被解析。

然后使用 window.onload 事件隐藏该 loading page ，预实现加载效果。

此方法适合于绝大多数应用，实现比较简单，当重新刷新页面时由于已经被缓存过，loading page 的时间会相应地缩短。

核心代码：
```javascript
window.onload = function(){
	var body = document.getElementsByTagName('body')[0],
		loadingWrap = document.getElementById('loading-wrap');

	body.removeChild(loadingWrap);
}
```

## 百分比效果 loading

实现百分比进度提示的关键在于首先获得需要预加载文件的总大小，然后实时显示 `加载完毕的文件/需要预加载文件` 总大小。

也是用到了 `onload` 事件。

核心代码：
```javascript
var
	body =  document.getElementsByTagName('body')[0],
	arrImg = document.getElementsByTagName('img'),
	loadingWrap = document.getElementById('loading-wrap'),
	loadingWrod = document.getElementById('loading'),
	length = 	arrImg.length,
	i = 0,
	j = 0;

for(; i<length; i++){
	var elem = arrImg[i];
	elem.onload = callback;
}

function callback(){
	j++;
	loadingWrod.innerText = (parseInt(j / length * 100)) + '%';

	// 所有图片加载完毕
	if(j == length){
		body.removeChild(loadingWrap);
	}
}
```
