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

```cpp title:auto-基础用法
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

auto GetName1() -> char* //c++14可以用auto类型函数 
{						//c++11可以用箭头 后置指定类型
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

```cpp title:auto-应用场景
#include <iostream>
#include <string>

#include <vector>
#include <unordered_map> 

class Device {};

//另一个类型
class DeviceManager
{
private:
	std::unordered_map<std::string, std::vector<Devices*>> m_Devices;
public:
	const std::unordered_map<std::string, std::vector<Devices*>>& GetDevices()
	{
		return m_Devices;
	}
};

int main()
{
	std::vector<std::string> strings;
	strings.push_back("Apple");
	strings.push_back("Orange");
	//使用迭代器
	for (auto it = strings.begin(); it != strings.end(); it++)
	{		//std::vector<std::string>::iterator 是个长类型直接改为auto
		std::cout << *it* << std::endl; 
	}
	
	
	using DeviceMap = std::unordered_map<std::string, std::vector<Devices*>>;
	//其实这个using可以直接丢到类里面
	
	//typedef std::unordered_map<std::string, std::vector<Devices*>> DeviceMap;
	//老版写法
	
	DeviceManager dm;
	//简化写法
	const DeviceMap& devices = dm.GetDevices();
	const auto& devices = dm.GetDevices(); //使用cost和& 减少复制 同时减少类型长度
	
	std::cin.get();
}
```