# CentOS

```bash
// Some code
docker run -itd --name="centos7f" centos:centos7
docker run -itd --privileged -p 22:22 -p 80:80 -p 8080:8080 --name="centos7f" centos:centos7 /sbin/init

// https://qiita.com/mikene_koko/items/4c71c969f55e3fe24190
// systemctlが使えるようにする。
docker run -itd --privileged -p 22:22 -p 80:80 -p 8080:8080 -p 3306:3306 --name="centos7f" centos:centos7 /sbin/init
docker run -itd --privileged -p 22:22 -p 80:80 -p 8080:8080 -p 3306:3306 --name="java_test" java_test:latest /sbin/init

docker exec -it centos7f /bin/bash
yum -y update
yum -y install openssh-server
systemctl start sshd.service

passwd （rootパスワード設定）
```
