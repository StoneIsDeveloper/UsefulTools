### Install BBR

[Blog](https://www.cyberciti.biz/faq/howto-reboot-linux/)

#### 把系统更新至最新
```
yum update -y
```

#### 安装支持BBR的内核
```
rpm --import https://www.elrepo.org/RPM-GPG-KEY-elrepo.org

rpm -Uvh http://www.elrepo.org/elrepo-release-7.0-2.el7.elrepo.noarch.rpm

yum --enablerepo=elrepo-kernel install kernel-ml
```

