## **TASK**

Analyze the home page loading of www.sjtu.edu.cn

Carry out your optimization solution

## **Repo**

网页加载方面感觉并没有发现什么。。。

可能页面中间的swiper加载的比较慢一点？（但是加载图片感觉本来就挺需要时间）

同时应该是因为页面设置的问题，左上角的SJTU LOGO的正确大小应该是依赖于swiper的（并没有研究出完整的影响途径），因此在swiper被加载出之前，SJTU LOGO的尺寸并不是很正确（特别是屏宽小的时候很明显）。

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