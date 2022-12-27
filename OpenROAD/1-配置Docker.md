# 写在前面
- 笔者之前没用过Docker，跑python环境就用conda，需要Linux就搞虚拟机，在学校服务器配环境需要用到sodu时就用[singularity](https://docs.sylabs.io/guides/3.5/user-guide/quick_start.html)，这次也是从零开始学习docker的使用

## 安装
- 网上有各种各样的安装方式，直接搜一个基本都行，官网上也有很多[https://docs.docker.com/engine/install/ubuntu/](https://docs.docker.com/engine/install/ubuntu/)
- 笔者这边想要在Ubuntu上安装docker-engine，尝试过网上的各种方法，最后都失败了，因为公司网络代理和权限的问题，经常无法访问各种网站，最终通过在本地下载安装包，然后上传至服务器再安装的方法，即为[https://docs.docker.com/engine/install/ubuntu/#install-from-a-package](https://docs.docker.com/engine/install/ubuntu/#install-from-a-package)
- Ubuntu上可以通过`cat /etc/os-release`查看自己的操作系统信息，`uname -a`查看自己的操作系统架构，`x86_64`即为`amd64`，之后按照[https://docs.docker.com/engine/install/ubuntu/#install-from-a-package](https://docs.docker.com/engine/install/ubuntu/#install-from-a-package)方法安装即可

## 基本操作
### 镜像（Image）
- 镜像是静态文件
- 镜像一般是只读的，不可修改
- 镜像启动之后变成容器实例
- 镜像理解为程序，是静态的，运行之后启动一个容器，容器是动态的，类似于进程
- 拉取镜像`docker pull <image_name>:<tag>`，如想要拉取ubuntu-18.04镜像，可以`docker pull ubuntu:18.04`
- `docker run -it <image>`
- `docker images`查看全部镜像
- [镜像使用](https://www.runoob.com/docker/docker-image-usage.html)

### 容器（Container）
- [容器使用](https://www.runoob.com/docker/docker-container-usage.html)
- `docker ps -a`查看全部container，包含已经停止运行的
- `docker ps -aq`只看container id
- `docker start <container>`将停止运行的容器恢复运行
- `docker stop <container>`停止一个正在运行的容器
- `docker cp <本地文件> <container_name>:<想要复制到哪里去>`从host向container复制文件，反过来就是从container复制到本机，可以这样先把apt用到的源复制过来，然后更新
- `docker rename <container_name_old> <container_name_new>`给container重命名
- `docker exec -it <container> bash`
  - exec表示运行一个container
  - i表示交互式
  - t表示伪终端
  - bash表示进来之后启动bash
  - 将`-it`换为`-d`表示后台运行

### 配置镜像源
- 就是docker从哪里拉取镜像
- [https://blog.csdn.net/houpk999/article/details/106693215](https://blog.csdn.net/houpk999/article/details/106693215)
- [https://cloud.tencent.com/developer/article/1806455](https://cloud.tencent.com/developer/article/1806455)
  - dockerd代理，守护进程dockerd使用的代理
  - container代理，容器运行阶段需要代理上网
  - docker build代理，构建image的时候需要配置的参数