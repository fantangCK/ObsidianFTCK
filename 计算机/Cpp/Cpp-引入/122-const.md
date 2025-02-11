---
tags:
  - Cpp
dlink:
  - "[[../../Cpp-目录|Cpp-目录]]"
---
```ad-note
title: const

保证不变量

- 虽然通过某种方式可以强制修改

```

```cpp title:const
#include <iostream>

class Entity()
{
private:
	int m_X, m_Y;
	//int* m_X, *m_Y;
	//注意 这里要两者都是指针的话 需要都加上*
	mutable int var; 
public;
	int GetX() const //这里声明就是保证这个方法不会修改变量
	//const int* const GetX() const //甚至有这种三重const 保证不改变
	{
		var = 2; //mutable保证在const下还能修改 但是这个一般用于debug  
		return m_X;
	}
	
	int GetX() //这里不包含const是一个 重载函数
	{
		return m_X;
		//此方法无法保证类中元素不被改变 在后面调用的时候会报错
	}
		
	void SetX(int x)
	{
		m_X = x; 
	}
}

void PrintEntity(const Entity& e)
{
	//默认是选择const的 即不修改类
	std::cout << e.GetX() << std::endl;
}


int main()
{
	Entity e;
	
	const int MAX_AGE = 10;
	
	const int* a = new int; //指针指向的内容为不变量
	
	a = (int*)&MAX_AGE; //此时做指针地址改变是合法的
	
	int* const b = new int; //指针指向内容可以改变 但指针的地址不能改变
	//主要区别主要看 const在星号*哪里
	
	*b = 2; //在此处是合法的
	
	const int* const c = new int; //指针的地址 和对应的元素全都不能改变
	
}


```

```ad-note
title: mutable

可改变的

- 配合const使用
- 用于lambda表达式

```

```cpp title:例子
代码
```