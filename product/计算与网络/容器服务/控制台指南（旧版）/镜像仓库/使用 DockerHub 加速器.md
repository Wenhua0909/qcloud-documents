>?容器服务旧版控制台目前已下线，文档已停止维护。新版控制台已进行了一系列模块的调整，建议参考 [新版用户指南](https://cloud.tencent.com/document/product/457/31697) 使用。

使用 DockerHub 加速器加速镜像，加速器会通过系统拉取镜像，本地对镜像进行缓存；已缓存镜像将直接返回，未缓存镜像将通过腾讯云加速服务进行下载返回。
Docker 软件源地址：
```
https://mirror.ccs.tencentyun.com
```
## CCS 集群 CVM 实例
无需手动配置，在创建节点时会自动安装 Docker 服务，配置 Mirror 镜像。配置项如下：
```shell
[root@VM_1_2_centos ~]# cat /etc/docker/dockerd 
IPTABLES="--iptables=false"
STORAGE_DRIVER="--storage-driver=overlay2"
IP_MASQ="--ip-masq=false"
LOG_LEVEL="--log-level=warn"
REGISTRY_MIRROR="--registry-mirror=https://mirror.ccs.tencentyun.com"
```
## CVM 实例配置
### Linux
- 适用于 Ubuntu14.04、Debian、CentOS 6 、Fedora 和 OpenSUSE 版本，其他版本可能有细微不同。
修改 Docker 配置文件 `/etc/default/docker`，如下：
```shell
DOCKER_OPTS="--registry-mirror=https://mirror.ccs.tencentyun.com"
```
- 适用于 CentOS 7 版本。
修改 Docker 配置文件 `vi /etc/sysconfig/docker`，如下：
```shell
OPTIONS='--registry-mirror=https://mirror.ccs.tencentyun.com'
```
>**注意：**
>Docker 1.3.2 版本以上才支持 Docker Hub Mirror 机制，如果您还没有安装 Docker 或者版本过低，请安装或升级版本。

### Windows
如果您使用的是 Boot2Docker，进入 Boot2Docker Start Shell 并执行：
```shell
sudo su echo "EXTRA_ARGS=\"–registry-mirror=https://mirror.ccs.tencentyun.com"">> /var/lib/boot2docker/profile  exit #  重启Boot2Docker
```
## 启动 Docker
执行如下命令
```shell
sudo service docker start
```
