---
tags:
  - Cpp
dlink:
  - "[[../../Cpp-目录|Cpp-目录]]"
---
```ad-note
title: 迭代器iterator

用于迭代数据集合(广义上的)内元素

```

```cpp title:迭代器iterator
#include <iostream>
#include <vector>

int main()
{
	std:vector<int> values = { 1, 2, 3, 4, 5 };
	//经典方法
	for (int i = 0 ; i < values.size(); i++)
	{
		std::cout << values[i] << std::endl;
	}
	//c++11之后的写法
	for (int value : values ) //能这么写内部是由一个迭代器实现的(STL源码)
		std::cout << value << std::endl;
	
	std::vector<int>::itera
	
	std::cin.get();
}
```