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
  
  暂无

+ 其它改进
  + 改善迷宫绘制，每次只更新一个块（而非整个迷宫）（其实本来就有这个函数。。。迷惑）
  + 改善迷宫绘制，每次绘画时重复多次执行fillRect()（以消除格子状的边界）
  + 改善stack中存入的数据
  + 优化一些逻辑
    + 绘画变得更快（遇到需要从栈取点的情况会一直pop直到遇到能延伸的点或栈为空）
    + creating mazes时禁用clear按钮
    + 解迷宫时移除canvas1的onMousedown事件
    + 解迷宫时禁用clear和create按钮
  + 删除了一些重复无用的代码片段

## **尚可优化部分**

+ 将迷宫的大小设置为响应式的（现有代码只会在初次渲染/点击Create后根据父级元素的大小确定迷宫长宽，单纯改变浏览器的窗口大小后迷宫大小仍然保持原样）
+ 封装迷宫
+ 重构代码……
+ 加入A*寻路
+ 优化UI

## **其它**

因为这个版本是copy周三时的版本的，并没有加入和优化maze2部分（没啥时间做……）