## 安装
按照官网进行就行

## 问题
### 第一步中的Prerequisites.Dockerfile需要去github上下载epic的carla，但是教程还是使用用户名密码登录，现在github已经不支持了，要用token，修改该文件中的50行为；
RUN git clone --depth 1 -b carla "https://$token$@github.com/CarlaUnreal/UnrealEngine.git" ${UE4_ROOT}

### fbx-sdk一直下载不下来
carla官网提供教程第二步编译中，由于autodesk官网限制非网址下载，所以docker脚本里wget结尾需要加上–no-check-certificate；另外，autodesk网址换成中文网址。具体步骤如下：
```
vim carla/Util/Docker/Carla.Dockerfile
```
在第12行插入以下命令用于替换文件中的网址和命令
```
  sed -i "s/autodesk.com/autodesk.com.cn/g" Util/BuildTools/BuildUtilsDocker.sh && \
  sed -i "s/-P "${CARLA_DOCKER_UTILS_FOLDER}"/-P "${CARLA_DOCKER_UTILS_FOLDER}" --no-check-certificate/g" Util/BuildTools/BuildUtilsDocker.sh && \
```
然后保存退出：
```
:wq
```

### 其他编译时候网络问题
失败了就重新开始，除了以上出现的问题，其余都是随机性的网络状态不佳导致的
