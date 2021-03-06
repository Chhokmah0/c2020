### 题目：寻径GA（遗传算法）

### 要求：

1. 任意给出一个迷宫地图（参见level1/p09_maze）,采用GA实现一个算法，寻找最佳路径
1. 绘制出最佳路径
1. 打印运算时间

### 参考：

[遗传算法入门](http://blog.csdn.net/zzwu/article/details/561577) 



- 每代个数：`5000`
- 基因长度（移动步数）：`100`
- 父代个数：`50`
- 变异：因为有`4`种任务（上下左右），随机选与原来不同的概率是`0.75`，接近`0.7`，所以直接挑一个变异
- 适应度：适应度用整数表示，直接选择最优秀的
	1. 撞墙：`-1`，增加有效步数
	2. 走重复路：`-5`，增加有效步数
	3. 走不重复路：`0`
	4. `减去离终点的距离`
	5. 到达终点：`+5000`，决定性区分优秀和劣质
- 每次找到一个可以到达终点的个体时，截短所有个体的基因
