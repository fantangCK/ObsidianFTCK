---
tags:
  - Cpp
dlink:
  - "[[../../Cpp-目录|Cpp-目录]]"
dg-publish: true
---
```ad-note
title: 调试工作
# 断点-break
1. 设置断点F9或者点击左侧边栏 
2. 确定处在Debug模式
3. F11逐语句运行 跳转到对应代码位置
4. F10逐过程运行
5. debug时还能设置第二个断点 F5继续运行（或者别的操作）可以跳到这里

# 运行状态-state
1. 查看变量: Local Watch Auto三个界面查看运行时变量变化
2. 查看内存: 调试-窗口-内存 工具内可用 &a跳转到对应的位置
```

```ad-note
title: Visual Studio 条件与操作断点
# 条件和操作断点
![](附件/Pasted%20image%2020250215221048.png)
实时调试
- 操作Action (打开继续运行的情况下 不勾选就停止在断点处 可以查看数据对应的值)
	- 例如 the mouse position is: {(float)x},{(float)y}
	- 运行中就在控制台输出设置的信息
- 条件Condition
	- 任何的布尔语句如 x == 5
这俩能一起用
```
