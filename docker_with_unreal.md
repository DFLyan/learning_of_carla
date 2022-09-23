## 安装
按照官网进行就行

## 问题
### fbx-sdk一直下载不下来
官网限制非网址下载，所以docker脚本里wget结尾需要加上–no-check-certificate；另外，autodesk网址换成中文网址。具体步骤如下：
```
vim carla/Util/Docker/Carla.Dockerfile  # 这
```
