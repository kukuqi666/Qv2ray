## 简介

linux环境是在kali 24.02上面测试的，其余的linux语言自行测试，因为有的linux发行版打开Applmages需要FUSE版本2才能运行
具体请参考[FUSE](https://github.com/AppImage/AppImageKit/wiki/FUSE)

## 下载通道
[Q2ray](https://github.com/Qv2ray/Qv2ray)

[v2ray-core](https://github.com/v2fly/v2ray-core)

[Xray-core](https://github.com/XTLS/Xray-core)

[trojan-go](https://github.com/p4gefau1t/trojan-go)

[v2rayA](https://github.com/v2rayA/v2rayA)

[v2ray-233boy](https://github.com/233boy/v2ray)

```
bash <(curl -s -L https://git.io/v2ray.sh)
```

[xray-233boy](https://github.com/233boy/Xray)

```
bash <(wget -qO- -o- https://github.com/233boy/Xray/raw/main/install.sh)
```

[v2ray-xyz690](https://github.com/xyz690/v2ray/tree/master)

```
bash <(curl -s -L https://raw.githubusercontent.com/xyz690/v2ray/master/install.sh)
```

[fhs-install-v2ray](https://github.com/v2fly/fhs-install-v2ray)

```
bash <(curl -L https://raw.githubusercontent.com/v2fly/fhs-install-v2ray/master/install-release.sh)
```

### 使用说明
1. 打开APPImage根据图片序号一步步操作 2和3是v2ray核心的可执行文件路径和资源目录(v2ray-core和xray-core用一个就行)
下载好核心文件以后放在用户根目录下或其他好找的目录(不知道怎么填路径进核心文件打开终端pwd打印一下路径) 然后把可执行文件的路径和资源路径填进去点5和6验证一下配置有没有问题

![image](https://github.com/kukuqi666/Qv2ray_tools/blob/main/images/IMG_20240722_132513.png)

2. 核心文件配置好接下来安装Qvplugin插件，插件的位置默认在/home/用户名/.config/qv2ray/plugins/路径下面，
下载好的插件(.so文件)用mv命令移动到默认位置下面，用户名是自己电脑的用户名

![image](https://github.com/kukuqi666/Qv2ray_tools/blob/main/images/IMG_20240722_132623.png)

3. 插件安装完理论上是可以用了 但是如果使用Trojan协议的节点可能会用不了，打开Trojan-go插件然后点击设定再点击Browse
   选择自己Trojan可执行文件的路径 点击test run 出现如下弹窗就说明成功了，接下来导入节点就可以愉快上网了
   
![image](https://github.com/kukuqi666/Qv2ray_tools/blob/main/images/IMG_20240722_132806.png)
