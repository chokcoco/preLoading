# preLoading
页面预加载，各类预加载方法示例

## 使用 window.onload 事件
将 loading page 写在一个 div 块中，并放在 body 内容的最前面，这样 loading page 将最先被解析。

然后使用 window.onload 事件隐藏该 loading page ，预实现加载效果。

此方法适合于绝大多数应用，实现比较简单，当重新刷新页面时由于已经被缓存过，loading page 的时间会相应地缩短。
 
## 百分比效果 loading
实现百分比进度提示的关键在于首先获得 DOM 文件总大小，然后实时显示 `加载完毕的文件/DOM` 总大小。
