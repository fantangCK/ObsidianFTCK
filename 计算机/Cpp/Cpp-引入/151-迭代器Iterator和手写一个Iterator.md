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
	
	//像是vector array带有下标的一般都可以用上面两种写法
	//非这种类型 或者要做一定操作情况下会用别的写法
	for(std::vector<int>::iterator it = values.begin();
		it !=values.end(); it++)
	{	//这里的end是最后一个元素之后的元素
		std::cout << *it << std::endl; //it是地址 *做解引用
	}
	
	
	//简化类
	using ScoreMap = std::unordered_map<std::string, int>; //无序表 哈希表
	//using ScoreMapConstIter = ScoreMap::const_iterator;
	//此处const_iterator 不改变原值
	//再Using Iter这种不多见 但使用上面简化类多见
	ScoreMap map;
	
	map["Cherno"] = 5;
	map["C++"] = 2;
	
	//for(ScoreMapConstIter) //不多见
	for (ScoreMap::const_iterator it = map.begin()
		it !=map.end(); it++)
	{
		//*it //这样引用也行 方便一点见下面
		auto& key = it->first; //first对应map的第一个
		auto& value = it->second;
		
		std::cout << key << "=" << value << std::endl;
	}
	
	std::cout << std::endl;
	
	//改进
	for (auto kv : map)
	{	//此处auto是调用了一个pair
		auto& key = kv.first;
		auto& value = kv.second;
		std::cout << key << "=" << value << std::endl;
	}
	//c++17之后引入结构化绑定 进一步改进
	for (auto [key, value] : map)
		std::cout << key << "=" << value << std::endl;
	
	std::cin.get();
}
```