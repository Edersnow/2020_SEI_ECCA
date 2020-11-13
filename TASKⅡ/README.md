## **TASK**

Write a webpage game: Maze

+ Code base：
https://github.com/zilinglius/maze.git

+ Requirements：
  + More efficient algorithm
  + Customized size of maze
  + Optional
    + UI Improvement
    + Animation
  + Markdown doc

## **改进**

+ 主要改进

+ 其它改进
  + 改善迷宫绘制，每次只更新一个块（而非整个迷宫）（其实本来就有这个函数。。。迷惑）
  + 删除了一些重复无用的代码片段

## **尚可优化部分**

+ 将迷宫的大小设置为响应式的（现有代码只会在初次渲染/点击Create后根据父级元素的大小确定长宽，单纯改变浏览器的窗口大小后迷宫大小仍然保持原样）
+ 在solve迷宫的动画执行的时候如果进行点击操作会出现各种bug（）
+ 封装迷宫