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
## 6. 密码输入错误清理
- git config --system --unset credential.helper

## 参考PDF
- [Git-Cheet-Sheet-ByGeekHour](../../归档/Asset/PDF/Git-Cheet-Sheet-ByGeekHour.pdf)
- [GitCheatSheet_byGeekHour_v1.0.0](../../归档/Asset/PDF/GitCheatSheet_byGeekHour_v1.0.0.pdf)
```

```ad-note
title: git流程

打开我们的项目，此时项目中是没有 .git 文件的
在你的项目文件夹里面【鼠标右击】弹出菜单
在【鼠标右击】弹出的菜单中，点击【Git Bash Here】
在命令窗口中输入：git init
在 Gitee 中我们刚刚新建的仓库里，去复制仓库的地址

- git remote add origin 你的仓库地址
- git pull origin master
- git add .
- git commit -m “提交项目”
- git push origin master

现在可以去 Gitee 你的仓库，刷新一下，本地项目上传到自己的 Git 仓库中啦！！！！
```
