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
public;
	int GetX() const //这里声明就是保证这个方法不会修改变量
	//const int* const GetX() const //甚至有这种三重const 保证不改变
	{
		return m_X;
	}
	
	void SetX(int x)
	{
		m_X = x; 
	}
}

int main()
{
	const int MAX_AGE = 10;
	
	const int* a = new int; //指针指向的内容为不变量
	
	a = (int*)&MAX_AGE; //此时做指针地址改变是合法的
	
	int* const b = new int; //指针指向内容可以改变 但指针的地址不能改变
	//主要区别主要看 const在星号*哪里
	
	*b = 2; //在此处是合法的
	
	const int* const a = new int; //指针的地址 和对应的元素全都不能改变
	
}


```