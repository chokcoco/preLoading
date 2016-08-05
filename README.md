# preLoading
页面预加载，各类预加载方法示例

+ 使用window.onload事件
将 loading page 写在一个 div 块中，并放在 body 内容的最前面，这样 loading page 将最先被解析。

然后使用 window.onload 事件隐藏该 loading page ，预实现加载效果。

此方法适合于绝大多数应用，实现比较简单，当重新刷新页面时由于已经被缓存过，loading page 的时间会相应地缩短。
 
