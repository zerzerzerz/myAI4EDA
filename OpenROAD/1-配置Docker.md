# 写在前面
- 笔者之前没用过Docker，跑python环境就用conda，需要Linux就搞虚拟机，在学校服务器配环境需要用到sodu时就用[singularity](https://docs.sylabs.io/guides/3.5/user-guide/quick_start.html)，这次也是从零开始学习docker的使用

## 安装
- 网上有各种各样的安装方式，直接搜一个基本都行，官网上也有很多[https://docs.docker.com/engine/install/ubuntu/](https://docs.docker.com/engine/install/ubuntu/)
- 笔者这边想要在Ubuntu上安装docker-engine，尝试过网上的各种方法，最后都失败了，因为公司网络代理和权限的问题，经常无法访问各种网站，最终通过在本地下载安装包，然后上传至服务器再安装的方法，即为[https://docs.docker.com/engine/install/ubuntu/#install-from-a-package](https://docs.docker.com/engine/install/ubuntu/#install-from-a-package)
- Ubuntu上可以通过`cat /etc/os-release`查看自己的操作系统信息，`uname -a`查看自己的操作系统架构，`x86_64`即为`amd64`，之后按照[https://docs.docker.com/engine/install/ubuntu/#install-from-a-package](https://docs.docker.com/engine/install/ubuntu/#install-from-a-package)方法安装即可

## 