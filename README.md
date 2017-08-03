# PuGu-chat

## 基本实现图
![还是有些小问题的](https://github.com/GzhiYi/PuGu-chat/blob/master/img/%E5%AE%8C%E6%88%90%E5%9B%BE.png)

## 问题或解决描述
1. 将及时聊天数据存放一个临时数组，如果需要后期可以在关闭或一段时间之后将数组数据保存在文件中(当然真正的聊天是不是这样有待考究)
2. 存放用到了vue的子父组件通信，也就是广播事件。因为我将"我方"的聊天数据定义为一个组件。
3. 较大难点是怎么把聊天最新数据呈现出来，一开始的解决方案是：
```
function scrollChat()
{
  var e=document.getElementById("div1")
  e.scrollTop=e.scrollHeight;
}
var s=setInterval("scrollChat()",200)//这里设定200毫秒将滚动条强制拉到底部
//当然，投机取巧总会有bug，这样的方法直接导致滚动条无法上拉。。

//最后实现用到了jquery，代码如下：
$(document).ready(function(){ //保持滚动条在最底部的jq实现，这段代码在广播事件后执行。
    $('#chatBody').scrollTop($('#chatBody')[0].scrollHeight);
})
```

## 初版图，未制作完毕
![还有时间什么的没有修改，待添加](https://github.com/GzhiYi/PuGu-chat/blob/master/img/%E5%9F%BA%E6%9C%AC%E6%A0%B7%E5%BC%8F.png)

未完备注：未用现有组件，先尝试下自己用vue实现，还有些地方要处理。有些逻辑未免和最终即使聊天一样，这个需要去写多几次相同的小页面或者去git找相同的实例。明早补充。
