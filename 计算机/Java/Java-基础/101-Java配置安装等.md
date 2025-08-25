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
        //大小写也要注意
    }
}
```

```ad-info
title: Java相关概念

这是一门面向对象编程的语言 和Cpp很像(指针 继承多态被简化 还有内存管理)
JVM虚拟机保证了代码在编译为class后 能在各种设备运行

Java SE - 标准级
Java EE - 企业级
Java ME -  <sub>真有人用这玩意开发嵌入式?</sub>
```

```ad-note
title:Java 在 linux 上
# 安装arch 系
详情可参考 archwiki

以OpenJDK为例
其所需要的都可以在archlinux软件仓库找到,故可通过pacman安装
版本与包名对照表参考archwiki,如下

```cardlink
url: https://wiki.archlinuxcn.org/wiki/Java
title: "archwiki链接"
host: wiki.archlinuxcn.org

```

```ad-example

| 版本                                                      | Headless JRE                                                                                      | Full JRE                                                                        | JDK                                                                             | 文献                                                                              | 源码                                                                              |
| ------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| [OpenJDK 23](https://openjdk.java.net/projects/jdk/23/) | [jre-openjdk-headless](https://archlinux.org/packages/?name=jre-openjdk-headless)<sup>包</sup>     | [jre-openjdk](https://archlinux.org/packages/?name=jre-openjdk)<sup>包</sup>     | [jdk-openjdk](https://archlinux.org/packages/?name=jdk-openjdk)<sup>包</sup>     | [openjdk-doc](https://archlinux.org/packages/?name=openjdk-doc)<sup>包</sup>     | [openjdk-src](https://archlinux.org/packages/?name=openjdk-src)<sup>包</sup>     |
| [OpenJDK 21](https://openjdk.java.net/projects/jdk/21/) | [jre21-openjdk-headless](https://archlinux.org/packages/?name=jre21-openjdk-headless)<sup>包</sup> | [jre21-openjdk](https://archlinux.org/packages/?name=jre21-openjdk)<sup>包</sup> | [jdk21-openjdk](https://archlinux.org/packages/?name=jdk21-openjdk)<sup>包</sup> | [openjdk21-doc](https://archlinux.org/packages/?name=openjdk21-doc)<sup>包</sup> | [openjdk21-src](https://archlinux.org/packages/?name=openjdk21-src)<sup>包</sup> |
| [OpenJDK 17](https://openjdk.java.net/projects/jdk/17/) | [jre17-openjdk-headless](https://archlinux.org/packages/?name=jre17-openjdk-headless)<sup>包</sup> | [jre17-openjdk](https://archlinux.org/packages/?name=jre17-openjdk)<sup>包</sup> | [jdk17-openjdk](https://archlinux.org/packages/?name=jdk17-openjdk)<sup>包</sup> | [openjdk17-doc](https://archlinux.org/packages/?name=openjdk17-doc)<sup>包</sup> | [openjdk17-src](https://archlinux.org/packages/?name=openjdk17-src)<sup>包</sup> |
| [OpenJDK 11](https://openjdk.java.net/projects/jdk/11/) | [jre11-openjdk-headless](https://archlinux.org/packages/?name=jre11-openjdk-headless)<sup>包</sup> | [jre11-openjdk](https://archlinux.org/packages/?name=jre11-openjdk)<sup>包</sup> | [jdk11-openjdk](https://archlinux.org/packages/?name=jdk11-openjdk)<sup>包</sup> | [openjdk11-doc](https://archlinux.org/packages/?name=openjdk11-doc)<sup>包</sup> | [openjdk11-src](https://archlinux.org/packages/?name=openjdk11-src)<sup>包</sup> |
| [OpenJDK 8](https://openjdk.java.net/projects/jdk8/)    | [jre8-openjdk-headless](https://archlinux.org/packages/?name=jre8-openjdk-headless)<sup>包</sup>   | [jre8-openjdk](https://archlinux.org/packages/?name=jre8-openjdk)<sup>包</sup>   | [jdk8-openjdk](https://archlinux.org/packages/?name=jdk8-openjdk)<sup>包</sup>   | [openjdk8-doc](https://archlinux.org/packages/?name=openjdk8-doc)<sup>包</sup>   | [openjdk8-src](https://archlinux.org/packages/?name=openjdk8-src)<sup>包</sup>   |

```
