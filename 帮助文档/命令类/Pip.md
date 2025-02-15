# pip 永久换源

## 清华源
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
 
## 阿里源
pip config set global.index-url https://mirrors.aliyun.com/pypi/simple/
 
## 换回默认源
pip config unset global.index-url


## pip 临时换源
 -i https://pypi.tuna.tsinghua.edu.cn/simple

 ##vcpkg-cmake  https://vcpkg.io/
vcpkg install [packages to install]
cmake -B [build directory] -S . -DCMAKE_TOOLCHAIN_FILE=[path to vcpkg]/scripts/buildsystems/vcpkg.cmake
