## Install SSR on CentOS

### 1. install wget
``` 
yum install wget 
```

### 2.install Shadowsocks
``` 
wget –no-check-certificate -O shadowsocks.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh
``` 

### 3.shadowsocks.sh 读取权限
``` 
chmod +x shadowsocks.sh
``` 

### 4. 设置你的 ss 密码和端口号
``` 
./shadowsocks.sh 2>&1 | tee shadowsocks.log
``` 

### 5.选择加密方式

这里选择 7 ，使用aes-256-cfb的加密模式

---
##　CentOS 7 Open post
关闭防火墙：

``` 
systemctl stop firewalld.service #停止firewall
systemctl disable firewalld.service #禁止firewall开机启动
``` 

