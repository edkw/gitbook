# コマンド集

```bash
// Some code
docker pull centos:latest
docker images
docker run -itd --privileged -p 2222:22 --name centos8 centos:latest /sbin/init

-it コンテナのプロセスにttyを割り当てる
-d コンテナをバックグラウンドで実行
-p ポート指定（ここではsshアクセスポートの変更）
-privileged systemctlコマンドを使えるようにしたいのでこのオプションを追加
-name 作成したコンテナに名前をつける
「-privileged」オプションを追加しないと、CentOSを使用する際に必要となる「systemctl」コマンドなどが利用できないので、使いたい方は追加しましょう。

docker ps
docker exec -it centos8 /bin/bash
docker exec -it {コンテナID} /bin/bash
yum -y update
最低限、インターフェースやルートの状態を確認したいので「iproute」もインストールしておきます。
yum -y install iproute
外部からCentOSへアクセスできるようにSSHを起動します。
yum -y install openssh-server
systemctl start sshd.service
systemctl status sshd.service
rootパスワードを設定
passwd
yum -y install passwd
コンテナ（CentOS7）へSSHアクセス
ssh -p 2222 root@localhost

コンテナの停止・起動・削除
docker stop centos7
docker ps -a
docker start centos7
docker stop centos7
docker rm centos7

イメージ削除
docker images
docker rmi 5e35e350aded (image id)
```
