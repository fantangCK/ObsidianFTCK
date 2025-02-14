---
tags:
  - Cpp
dlink:
  - "[[../../Cpp-目录|Cpp-目录]]"
---
```ad-note
title: lambda匿名函数

快速的一次性代码

只要有一个函数指针就可以用lambda代替
函数指针参考[127-栈作用域生存期,智能指针,函数指针](127-栈作用域生存期,智能指针,函数指针.md)

```

```cpp title:lambda匿名函数
#include <iostream>
#include <vector>
#include <algorithm>

void ForEach(const std::vector<int> values, void(*func)(int))
{
	for (int value : values)
		func(value);
}

int main()
{
	std::vector<int> values = { 1, 5, 4, 2, 3 };

	//lambda语法分析(C++11引入的) [捕获] (传入参数) { 要运行的东东 }
	/*
	[捕获]		在lambda中使用外部变量
	(传入参数)	
	*/
	int a = 5;
	
	auto lambda = [](int value) { std::cout << "Value: " << std::endl; }
	ForEach(values, lambda);
	std::cin.get();
}

```