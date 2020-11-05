##

## **其它**

在观察网页的时候，我发现了一个小bug：随着不断进行页面上滚/下滚的操作，页面左上角的浮动div的位置开始发生变化。翻看相关源码，这部分似乎是使用了一种累计的方法计算这个div应有的位置：
```
    var lastscroll=0
    function heartBeat(){
        var diffY=0;
        if (document.documentElement && document.documentElement.scrollTop){
            diffY = document.documentElement.scrollTop;
        }else if (document.body){
            diffY = document.body.scrollTop
        }
        // console.log(diffY);

        var percent=diffY-lastscroll;

        document.getElementById("leftDIV1").style.top=parseInt(document.getElementById("leftDIV1").style.top)+percent+"px";
        
    }

    window.setInterval("heartBeat()",1);
```

但是这里检测函数的运行是有时间间隔的（虽然很短）。应该是这种间隔，加上使用了累计方法，导致左上角浮动的div位置偏离。