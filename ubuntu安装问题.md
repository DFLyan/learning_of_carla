# 在服务器上安装（没成功）
## ubuntu18
### 在anaconda环境下，会找不到"pyconfig.h"，需要"conda deactivate"退出anaconda的环境。

## ubuntu20
### 会用到clang 8，不安装会没法make pythonapi
```
sudo add-apt-repository -r "deb http://apt.llvm.org/xenial/ llvm-toolchain-xenial-8 main" &&
sudo apt install clang-8
```

# 在windows子系统上安装
## make launch
这一步可能会失败很多次，每次失败，重新make就行
