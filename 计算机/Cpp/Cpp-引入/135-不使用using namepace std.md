---
tags:
  - Cpp
dlink:
  - "[[../../Cpp-目录|Cpp-目录]]"
---
```ad-note
title: 不使用using namepace std

## 原因:
- 使用std可以指出使用的是标准模板库和c++库(EASTL 和标准 STL)
	- 不同命名法区别
		- 帕斯卡命名法-每个单词首字母大写,中间不得有空格下划线
		- 驼峰命名法-首字母大写...(待补充区别)
		- 蛇形命名法-Cpp写法

---

## 注意:
- using namespace std在于作用域 不在作用域内的函数等还是要写std的

```

```cpp title:案例
#include



namespace apple;

namespace orange;

using namespace apple;

int main()
{
	pri
}
```