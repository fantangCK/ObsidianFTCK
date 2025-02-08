#pip永久换源

##清华源
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
 
##阿里源
pip config set global.index-url https://mirrors.aliyun.com/pypi/simple/
 
##换回默认源
pip config unset global.index-url


##pip临时换源
 -i https://pypi.tuna.tsinghua.edu.cn/simple

 ##vcpkg-cmake  https://vcpkg.io/
vcpkg install [packages to install]
cmake -B [build directory] -S . -DCMAKE_TOOLCHAIN_FILE=[path to vcpkg]/scripts/buildsystems/vcpkg.cmake

 #cmake

 #conda

 channel_priority: strict
show_channel_urls: true
default_channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
envs_dirs:
  - E:\ProgramProject\Anaconda3\envs

#服务sc

##列出服务
sc query type=service state= all
加上 > log.log 输出日志

##启动/停止服务
sc [start/stop/pause/continue] [服务名]

##删除服务
sc delete [服务名]

#git设置
##1. 设置代理
添加 HTTP 和 HTTPS 代理：

git config --global http.proxy http://127.0.0.1:10809
git config --global https.proxy http://127.0.0.1:10809
添加 Socks5 代理：

git config --global http.proxy socks5://127.0.0.1:10808
git config --global https.proxy socks5://127.0.0.1:10808
##2. 检查当前 Git 代理
git config --global --get http.proxy
git config --global --get https.proxy
##3. 测试代理是否正常
尝试通过 Git 克隆一个公共仓库，例如：

git clone https://github.com/comfyanonymous/ComfyUI.git
如果克隆成功且速度正常，则说明代理设置成功。

##4. 查看Git所有配置
git config -l
##5. 取消添加的代理
git config --global --unset http.proxy
git config --global --unset https.proxy