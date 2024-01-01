# コマンド



## シャットダウン

```bash
shutdown -h now
```

## 再起動

```bash
shutdown -r now
```

## ディレクトリ内のファイル一覧

```bash
ls /etc/init.d/a* | xargs -i basename {}
```

## ファイル検索

```bash
find / -name test.txt
```
