---
tags:
  - 帮助
dlink:
  - "[[../帮助-目录|帮助-目录]]"
---
```ad-info
title:hipnc转hip流程
- 打开你的hipnc文件
- 点击最上方的菜单 Windows - Hscript Textport
- 在打开的窗口中输入 opscript -G -r / > $TEMP/temp.cmd
	- 按 Enter。该命令应该将您的场景转储到 $TEMP/temp.cmd 文本文件
- 现在打开一个空的 hip 文件。
	- 在Hscript Texport  键入以下命令cmdread $ TEMP / temp.cmd 将从$ TEMP读取temp.cmd
```
