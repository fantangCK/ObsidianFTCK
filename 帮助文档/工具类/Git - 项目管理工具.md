---
tags:
  - 帮助
dlink:
  - "[[../帮助-目录|帮助-目录]]"
---
```ad-note
title: git常用命令
# git 设置
## 1. 设置代理
### 添加 HTTP 和 HTTPS 代理：

- git config --global http.proxy http://127.0.0.1:10809
- git config --global https.proxy http://127.0.0.1:10809
### 添加 Socks 5 代理：

- git config --global http.proxy socks5://127.0.0.1:1080
- git config --global https.proxy socks5://127.0.0.1:10808
## 2. 检查当前 Git 代理
 - git config --global --get http.proxy
 - git config --global --get https.proxy
## 3. 测试代理是否正常
尝试通过 Git 克隆一个公共仓库，例如：

- git clone https://github.com/comfyanonymous/ComfyUI.git
如果克隆成功且速度正常，则说明代理设置成功。

## 4. 查看 Git 所有配置
- git config -l
## 5. 取消添加的代理
- git config --global --unset http.proxy
- git config --global --unset https.proxy

```
