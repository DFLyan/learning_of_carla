# 来源于[官网（windows版本）](https://carla.readthedocs.io/en/latest/build_windows/)
**建议安装的都根据官网推荐来，特别是VS，不然后面改配置报错很麻烦，而且会衍生很多看不懂的报错**
# 一 依赖安装
## 1.1. VS、python、cmake、git、make等等
**make安装后需要手动添加系统路径，C:\Program Files (x86)\GnuWin32\bin**
## 1.2. Unreal Engine（需要按照官网先把epic和github帐号链接，然后会受到epic邀请加入github组的邮件，加入后才能后续git clone相关代码）
### 后面就跟着官网来就行了，源码编译和epic官网下载客户端应该没有太大区别，之前的版本是直接下载客户端；第二步可能要安装.NETFramework,根据提示下载安装就好了。

# 二 carla安装
## 2.1 Get assets
在这一步，开始下载后要注意打开任务管理器看网速，啥时候没网速了，应该是下载完了（地址：E:\carla\carla\Unreal\CarlaUE4\Content\Carla；大小：13.1G），然后要按回车，不然不会自动开始解压（以下在x64 native tools command...下进行的所有命令，如果长时间没反应，可以尝试按下回车键）。解压需要提前安装7zip软件。
## 2.2 Build CARLA（这里的报错基本是修改E:\carla\carla\Util\InstallersWin下的.bat文件解决）
### 2.2.1 zlib报错，我安装的时候，[官网](http://www.zlib.net/)版本是12了，所以E:\carla\carla\Util\InstallersWin\install-zlib.bat下设置的11就会下载不了，右击编辑，修改成1.2.12就行。
### 2.2.2 libpng报错，同样的，修改地址：set LIBPNG_REPO=http://downloads.sourceforge.net/gnuwin32/files/libpng-%LIBPNG_VERSION%-src.zip
### 2.2.3 rpclib git clone后出现head detach，直接把bat文件中的-b “"%RPC_VERSION%"”去掉
### 2.2.4 Cmake Error错误，因为我安装的是vs2022，通过cmake --help命令可知，要把.bat里出现Visual Studio 16 2019，都改成Visual Studio 17 2022.
### 2.2.5 boost报错，同样要修改下toolset的版本，vs2022是14.3（msvc-14.2-->14.3;vc141-->vc143），E:\carla\carla\Util\BuildTools\setup.bat也要改
### 2.2.6 buildlibcarla报错，同样修改版本E:\carla\carla\Util\BuildTools\buildlibcarla.bat,Visual Studio 16 2019，都改成Visual Studio 17 2022

