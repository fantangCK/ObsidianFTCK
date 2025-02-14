---
tags:
  - Cpp
dlink:
  - "[[../../Cpp-目录|Cpp-目录]]"
---
```ad-note
title: auto

自动猜出变量类型

不过项目中尽量不要用auto 一眼看得出来类型是最好的
当api类型改变 影响了函数的调用会导致更多的问题


```

```cpp title:auto
#include <iostream>
#include <string>

std::string GetName()
{
	return "Cherno";
}

char* GetName1()
{
	return "Cherno";
}

int main()
{
	int a = 5;
	
	auto b = a; //b的类型自动就判断为int
	auto c = 5.5L; //自动变为long类型
	auto d = 5.5f; //自动变为float类型
	auto e = “Cherno”; //自动变为char类型
	
	auto name = GetName(); //自动推断什么类型 不用在两边都改
	
	auto name = GetName1(); 
	int tmp = name.size();	//如果使用auto 这里就没办法调用了
	
	std::string name =GetName1();//这样是可以操作的 包含了一次隐式转换
	//后续的size操作方法也是可以用的
	
	std::cout << b << std::endl
	
	std::cin.get();
}
```