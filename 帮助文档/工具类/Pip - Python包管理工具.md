---
tags:
  - 帮助
dlink:
  - "[[../帮助-目录|帮助-目录]]"
---

```ad-note
title:pip常用命令

# pip 永久换源

## 清华源
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
 
## 阿里源
pip config set global.index-url https://mirrors.aliyun.com/pypi/simple/
 
## 换回默认源
pip config unset global.index-url


## pip 临时换源
 -i https://pypi.tuna.tsinghua.edu.cn/simple

```
