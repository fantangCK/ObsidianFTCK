---
dg-publish: true
dg-home: true
---
# 这里是数字花园首页

> [!example]+ 索引
> ```dataview
> list
> from ""
> where contains(file.path,"计算机/") and contains(file.name,"-目录")
> sort file.name
> ```