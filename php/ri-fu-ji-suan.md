# 日付計算



## 月の引き算

```php
// 現在日付の１か月前
$result_date = date("Ym ", mktime(0, 0, 0, date("m") - 1, date("d") , date("Y")));
```
