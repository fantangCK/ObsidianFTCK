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
#include <iostream>
#include <string>

namespace apple{
	void print(const std::string& text)
	{
		std::cout << temp << std::endl;
	}
}

namespace orange{
	void print(const char* text)
	{
		std::string temp = text;
		std::reverse(temp.begin(), temp.end());
		std::cout << temp << std::endl;
	}
}


using namespace apple;
using namespace orange;

int main()
{
	print("Hello");	//const char类型 默认是走orange命名空间
					//如果走apple命名空间涉及一个隐式转换
	
	std::cin.get()
}
```