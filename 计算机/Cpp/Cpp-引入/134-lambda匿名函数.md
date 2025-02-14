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

cpp参考手册如下

```cardlink
url: https://zh.cppreference.com/w/%E9%A6%96%E9%A1%B5
title: "cppreference.com"
host: zh.cppreference.com
```


```cpp title:lambda匿名函数
#include <iostream>
#include <vector>
#include <algorithm>

#include <functional>
											//原始函数指针
//void ForEach(const std::vector<int> values, void(*func)(int))
void ForEach(const std::vector<int> values, const std::function<void(int)>& func)
{											
	for (int value : values)
		func(value);
}

int main()
{
	std::vector<int> values = { 1, 5, 4, 2, 3 };
	
	std::fun_if(values.begin(), value.end(), [](int value))
	
	//lambda语法分析(C++11引入的) [捕获] (传入参数) { 要运行的代码 }
	/*
	[捕获]		在lambda中使用外部变量 值传递(有复制) 引用传递
		[=]	值传递所有变量
		[&]	引用传递所有参数
	
	(传入参数)	mutable
	
	*/
	int a = 5;
	
	auto lambda = [=](int value) mutable {
		a = 5;	//这里改变是不允许的 即使 使用的是值传递 加上mutable就行
		std::cout << "Value: " << value << a << std::endl;
	}
	ForEach(values, lambda);
	std::cin.get();
}

```