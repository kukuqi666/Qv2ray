
## 安装 v2rayA

### 方法一：通过软件源安装

#### 添加公钥

```bash
wget -qO - https://apt.v2raya.org/key/public-key.asc | sudo tee /etc/apt/keyrings/v2raya.asc
```

#### 添加 V2RayA 软件源

```bash
echo "deb [signed-by=/etc/apt/keyrings/v2raya.asc] https://apt.v2raya.org/ v2raya main" | sudo tee /etc/apt/sources.list.d/v2raya.list
sudo apt update
```

#### 安装 V2RayA

```bash
sudo apt install v2raya v2ray ## 也可以使用 xray 包
```

### 方法二：手动安装 deb 包

#### 下载v2raya的安装包
[从 Release 下载 v2rayA 的 deb 包](https://github.com/v2rayA/v2rayA/releases)后可以使用 Gdebi、QApt 等图形化工具来安装，也可以使用命令行：

```bash
sudo  dpkg -i installer_debian_xxx_vxxx.deb ### 自行替换 deb 包所在的实际路径
```
#### 下载v2ray或xray的核心文件
[从 Release 下载 v2ray的压缩包](https://github.com/v2fly/v2ray-core/releases/)
或者
[从 Release 下载 xray 的压缩 包](https://github.com/XTLS/Xray-core/releases)
解压之后把v2ray或者xray的二进制文件移动到/usr/local/bin目录 然后赋予可执行权限
然后把压缩包里面的geoip.dat 和geosite.dat移动到~/.local/share/v2ray或~/.local/share/xray目录里面

    V2Ray 资源目录：/run/user/0/v2raya
    
    v2rayA 工作目录：/root
    
    v2rayA 配置文件目录：/etc/v2raya

通常情况下，V2Ray 的核心文件（如 v2ray 或 v2ray.exe）可能位于以下目录之一：

    资源目录：/run/user/0/v2raya
    
    工作目录：/root
    
    系统默认路径：如 /usr/bin/v2ray 或 /usr/local/bin/v2ray



V2Ray / Xray 的 deb 包可以在 [APT 软件源中](https://github.com/v2rayA/v2raya-apt/tree/master/pool/main/)找到。


下载地址→https://github.com/kukuqi666/Qv2ray/releases/tag/v2rayA

## 启动 v2rayA / 设置 v2rayA 自动启动

### 在终端直接启动
```bash
╭─root@ubuntu ~
╰─➤  v2raya
╭─root@ubuntu ~
╰─➤  v2ray
```
> 从 1.5 版开始将不再默认为用户启动 v2rayA 及设置开机自动。

- 启动 v2rayA

  ```bash
  sudo systemctl start v2raya.service
  ```

- 设置开机自动启动

  ```bash
  sudo systemctl enable v2raya.service
  ```

<!-- ## 切换 iptables 为 iptables-nft

对于 Debian11 用户来说，iptables 已被弃用。安装 iptables 后，Debian 会自动设置使用 iptables-nft 作为后端。

安装 iptables，自动启用 iptables-nft：

```bash
apt install iptables
```

也可以手动设置使用 nftables 作为 iptables 的后端以进行适配：

```bash
update-alternatives --set iptables /usr/sbin/iptables-nft
update-alternatives --set ip6tables /usr/sbin/ip6tables-nft
update-alternatives --set arptables /usr/sbin/arptables-nft
update-alternatives --set ebtables /usr/sbin/ebtables-nft
```

如果你想切换回 legacy 版本：

```bash
update-alternatives --set iptables /usr/sbin/iptables-legacy
update-alternatives --set ip6tables /usr/sbin/ip6tables-legacy
update-alternatives --set arptables /usr/sbin/arptables-legacy
update-alternatives --set ebtables /usr/sbin/ebtables-legacy
```

切换后重启即可。 -->

## 使用 nftables

如果你的系统上已经有了 `nftables` 防火墙，那么 v2rayA 将优先使用 `nft` 命令来创建防火墙规则。可以使用 `--nftables-support` 参数或者 `V2RAYA_NFTABLES_SUPPORT` 来进行控制是否开启 nftables 支持。
