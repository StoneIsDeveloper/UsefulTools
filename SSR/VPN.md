## Install SSR on CentOS

#### 1. install wget
``` 
yum install wget 
```

#### 2.install Shadowsocks
``` 
wget –no-check-certificate -O shadowsocks.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh
``` 

#### 3.shadowsocks.sh 读取权限
``` 
chmod +x shadowsocks.sh
``` 

#### 4. 设置你的 ss 密码和端口号
``` 
./shadowsocks.sh 2>&1 | tee shadowsocks.log
``` 

#### 5.选择加密方式

这里选择 7 ，使用aes-256-cfb的加密模式

---
## CentOS 7 Open post
### Centos 7 firewall 命令
### 关闭防火墙：

``` 
systemctl stop firewalld.service #停止firewall
systemctl disable firewalld.service #禁止firewall开机启动
``` 

#### 查看已经开放的端口：
``` 
firewall-cmd --list-ports
``` 
### 开启端口
``` 
firewall-cmd --zone=public --add-port=80/tcp --permanent
``` 


>命令含义：

>–zone #作用域

>–add-port=80/tcp #添加端口，格式为：端口/通讯协议

>–permanent #永久生效，没有此参数重启后失效

### 重启防火墙
``` 
firewall-cmd --reload            #重启firewall
systemctl stop firewalld.service #停止firewall
systemctl disable firewalld.service    #禁止firewall开机启动
firewall-cmd --state                   #查看默认防火墙状态（关闭后显示notrunning，开启后显示running）

``` 






