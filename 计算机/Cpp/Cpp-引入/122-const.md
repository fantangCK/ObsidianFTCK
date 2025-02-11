---
tags:
  - Cpp
dlink:
  - "[[../../Cpp-目录|Cpp-目录]]"
---
```ad-note
title: const

1

```

```cpp title:const
#include <iostream>

int main()
{
	const int MAX_AGE = 10;
	
	const int* a = new int; //指针指向的内容为不变量
	
	a = (int*)&MAX_AGE; 
	
	int* const a = new int; //指针的
	
	
}


```