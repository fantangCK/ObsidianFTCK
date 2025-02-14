---
tags:
  - Cpp
dlink:
  - "[[../../Cpp-目录|Cpp-目录]]"
---
```ad-note
title: auto

自动猜出变量类型

```

```cpp title:auto
#include <iostream>
#include <string>

int main()
{
	int a = 5;
	
	auto b = a; //b的类型自动就判断为int
	auto c = 5.5L; //自动变为long类型
	auto d = 5.5f; //自动变为float类型
	auto e = “Cherno”; //自动变为char类型
	
	
	std::cout << b << std::endl
	
	std::cin.get();
}
```