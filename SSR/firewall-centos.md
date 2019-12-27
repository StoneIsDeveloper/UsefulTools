## CentoOS 7  
#### 1首先查看防火墙状态：
```
firewall-cmd --state
```

>未识别的命令 firewall-cmd
#### 2.install firewall
```
yum install firewalld 
```

>not running

### firewalld 的基本使用

启动： 
```
systemctl start firewalld
```

关闭： 
```
systemctl stop firewalld
```
查看状态： 
```
systemctl status firewalld
```
开机禁用 ： 
```
systemctl disable firewalld
```
开机启用 ： 
```
systemctl enable firewalld
```
查看开放的端口：
```
firewall-cmd --list-ports
```
添加端口：
```
firewall-cmd --add-port=8080/tcp --permanent
```
>–permanent永久生效，没有此参数重启后失效
