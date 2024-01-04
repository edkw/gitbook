# シェル

## 世代バックアップ

Mysqlのダンプファイル作成及び特定のディレクトリに7世代分バックスクリプト。

```bash
#!/bin/sh

# 他のユーザからバックアップを読み込めないようにする
umask 077

# バックアップファイルを何日分残しておくか（一ヶ月分）
period=7
# バックアップファイルを保存するディレクトリ
dirpath='/home/user/backup/mysql'

# ファイル名を定義(※ファイル名で日付がわかるようにしておきます)
filename=`date +%y%m%d`

# mysqldump実行（ファイルサイズ圧縮の為gzで圧縮しておきます。）
mysqldump -u root --password=******** -h localhost bellanotte | gzip > $dirpath/$filename.sql.gz

# 古いバックアップファイルを削除
oldfile=`date --date "$period days ago" +%y%m%d`
rm -f $dirpath/$oldfile.sql.gz

```
