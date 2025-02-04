---
tags:
  - 计算机
dlink:
---
# 一、引入
## 1. C++运行逻辑-编译原理

###  概念：
```ad-note
title: 申明
告诉编译器 函数存在

<font color="#2DC26B">只需要包含函数声明即可</font>
```
```cpp title:例子
void Log(const char* message);
```

```ad-note
title: 定义
告诉编译器 函数到底是什么

<font color="#2DC26B">需要包含函数整体</font>
```
```cpp title:例子
void Log(const char* message)
{
    std::cout << message << std::endl;
}
```

###  预处理阶段：

```cpp title:'预处理中 include作用'
#include <iostream> 
//只是将所有内容复制到引入的地方
```
###  编译阶段：
###  链接阶段：

# 二、STL 库

# 三、案例
