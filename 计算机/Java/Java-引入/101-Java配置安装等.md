---
tags:
  - Java
dlink:
  - "[[../../Java-目录|Java-目录]]"
---
```ad-note
title: 配置安装

# 流程
- 安装Java(推荐使用BellSoft的LibericaJDK 优秀的开源协议 比Oracle好)
	- 配置环境变量等等
- 安装eclipse(可附加汉化包等)
- 实际还是用intelliJ IDE吧(学习版操作方法自查 可用jar 也可以学生认证)
```

```Java title:第一个Hello World
/* HelloWorld.java */
public class HelloWorld {
 			//注意本文件名一定要和类名是一致的
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

```ad-info
title: Java相关概念

这是一门面向对象编程的语言 和Cpp很像(指针 继承多态被简化 还有内存管理)
JVM虚拟机保证了代码在编译为class后 能在各种设备运行

Java SE
Java EE
```
