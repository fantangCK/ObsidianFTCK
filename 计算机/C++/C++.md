---
tags:
  - 计算机
---
# 一、引入
## 1. C++运行逻辑-编译原理

###  概念

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

###  预处理阶段

```cpp title:'预处理'
#include <iostream> 
//只是将所有内容复制到引入的地方

#if 1
//if后面为1即True 中间部分内容才会在预处理过程中被引入
#endif
```
###  编译阶段
```ad-note
title: 编译Build
将源代码转换为机器代码或汇编代码的过程。
在这个阶段，编译器会对每个源文件进行词法分析、语法分析、语义分析、优化和代码生成。
通过这些步骤，编译器会检查代码中的语法错误和语义错误，并将代码转换为目标文件（*.obj*）
这些目标文件通常包含机器码和一些符号信息，但还不能直接运行。

```

###  链接阶段

```ad-note
title: 链接Link
链接阶段就像是将这些单独翻译好的故事片段连接成一本完整的书。在这个过程中，链接器会将所有这些片段（目标文件）组合在一起，并且填充那些在翻译过程中留下的空缺（符号引用），比如你在故事中提到的某个角色，但是在某个片段中没有详细介绍。链接器会找到这个角色的详细描述，并将其插入到合适的位置

```

### 报错分析

Visual Studio报错中
- 以 Cxxxx 的报错，即发生在 Compile 编译阶段
- 以 LNKxxxx 的报错，即发生在 Linking 链接阶段
# 二、STL 库

# 三、案例
