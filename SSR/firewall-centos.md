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

>after added new port, need to restart firewall

---
### Fix issue 
when excute
```
firewall-cmd --list-ports
```
return
>FirewallD is not running

when excute
```
systemctl enable firewalld

systemctl start firewalld

systemctl status firewalld
```
return message1
```
● firewalld.service - firewalld - dynamic firewall daemon
   Loaded: loaded (/usr/lib/systemd/system/firewalld.service; enabled; vendor preset: enabled)
   Active: inactive (dead) since Fri 2019-12-27 07:23:21 UTC; 16s ago
     Docs: man:firewalld(1)
  Process: 17894 ExecStart=/usr/sbin/firewalld --nofork --nopid $FIREWALLD_ARGS (code=exited, status=0/SUCCESS)
 Main PID: 17894 (code=exited, status=0/SUCCESS)

Dec 27 07:23:21 hwsrv-611769.hostwindsdns.com systemd[1]: Starting firewalld - dynamic firewall daemon...
Dec 27 07:23:21 hwsrv-611769.hostwindsdns.com firewalld[17894]: ERROR: Exception DBusException: org.fr...le
Dec 27 07:23:21 hwsrv-611769.hostwindsdns.com systemd[1]: Started firewalld - dynamic firewall daemon.
Hint: Some lines were ellipsized, use -l to show in full.
```
when 
```
 systemctl restart firewalld

```
return message1

then 
```
sudo reboot
```

then check status

```
systemctl status firewalld
```

working !

```
● firewalld.service - firewalld - dynamic firewall daemon
   Loaded: loaded (/usr/lib/systemd/system/firewalld.service; enabled; vendor preset: enabled)
   Active: active (running) since Fri 2019-12-27 07:29:02 UTC; 1min 48s ago
     Docs: man:firewalld(1)
 Main PID: 592 (firewalld)
   CGroup: /system.slice/firewalld.service
           └─592 /usr/bin/python2 -Es /usr/sbin/firewalld --nofork --nopid

```
















