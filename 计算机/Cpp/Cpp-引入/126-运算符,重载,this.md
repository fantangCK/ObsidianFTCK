---
tags:
  - Cpp
dlink:
  - "[[../../Cpp-目录|Cpp-目录]]"
---
```ad-note
title: 函数重载

函数重载是指同一个函数名可以根据参数类型、数量或顺序不同，定义多个函数版本。这样同一个函数名可以处理不同的情况

```

```ad-note
title: 操作符
operator-操作符

+ = , () <<等等都是操作符

```

```cpp title:重载函数与操作符
#inlcude <iostream>
#include <string>

struct Vector2{
	float x ,y;
	
	Vector2(float x, float y)
		: x(x), y(y) {}
	
	Vector2 Add(const Vector2& other) const
	{
		return Vector2(x + other.x, y + other.y);
		//另一种写法
		//return operator+(other);
		//或者return *this + other;
	}
	
	Vector2 operator+(const Vector2& other) const
	{		//operator表示的是运算符
			//此处表示如果操作符是+
		return Add(other);
		//另一种写法 配合上面的
		//return Vector2(x + other.x, y + other.y);
	}
	
	Vector2 Multiply(const Vector2& other) const
	{
		return Vector2(x * other.x, y * other,y);
	}
	
	Vector2 operator*(const Vector2& other) const
	{
		return Multiply(other);
	}
	
	bool operator==(const Vector& other) const
	{
		return x == other.x && y ==other.y;
	} //对于==操作符重载
	
	bool operator !=(const Vector& other) const
	{
		return !operator==(other);
		//同理 !(*this == other)
		
	}
	
}

std::ostream& operator<<(std::string& stream, const Vector2& other)
{
	stream << other.x << "," << other.y;
	return stream;
} //运算符重载 最好是不要经常干 代码风格就是一坨

int main()
{
	Vector2 position(4.0f,4.0f);
	Vector2 speed(0.5f,1.5f);
	Vector2 powerup(1.1f,1.1f);
	Vector2 result1 = position.Add(speed.Multiply(powerup));
											//难以理解
	//Cpp下采用下面的方法 Java中只能做如上操作
	Vector2 result2 = position + speed * powerup;
	
	std::cout << result2 << std::endl; //默认是没有这个操作的
	
	if (result1 == result2) {}	
	std::cin.get();
}
```

```ad-note
title: this 关键字

类中对象的指针

```

```cpp title:this
#include <iostream>
#include <string>

void PrintEntity(Entity* e);

void PrintEntity1(const Entity& e);

class Entity
{
public:
	int x,y;
	Entity(int x,int y)
	{	
		/*
		Entity* e = this;//默认此e就是const this指向是可以改变的 即普通指针
		e->x = x;
		*/ //等价于
		this->x = x; //因为intx和输入的x是一样的名字 需要这样操作
		//等价于(*this).x = x;
		this->y= y;
		
		PrintEntity(this); //类中调用 类外的函数 入口参数直接用this表示Entity本身
		PrintEntity1(*this); //使用引用const方法这样操作
		
		//非引用const方法
		Entity& e = *this;
		
		delete this; //除非特殊要求 不要使用该方法 该方法是在释放类中参数空间
	}
	int GetX() const
	{
		const Entity* e = this; //因为此方法是const 所以对应的变量也要是const的
		//但是此处this指向是不能改变的
	}
};

void PrintEntity(Entity* e)
{
	//Do sth.
}

int main()
{
	std:cin.get();
}
```