# Laravel



## プロジェクト作成

```bash
composer create-project laravel/laravel example-app
```

### キー作り直し

```bash
php artisan key:generate
```

## 簡易サーバー

```bash
php artisan serve
```

## バッチ作成

php artisan make:command YourCommand

## ３つのファイルを作成

```bash
php artisan make:model [YourModelName] -mcr
```

* `m` オプション : モデルの作成と同時にマイグレーションファイルを作成
* `c` オプション : モデルの作成と同時にControllerファイルを作成
* `r` オプション : 作成するControllerファイルにデフォルトでCRUDのためのアクションを追加

### Model

```bash
php artisan make:model [YourModelName]
```

### Controller

```bash
php artisan make:controller [YourControllerName]
```

### Migration

```bash
php artisan make:migration create_users_table
```

## Migration

### status

```bash
php artisan migrate:status
+------+------------------------------------------------+-------+
| Ran? | Migration                                      | Batch |
+------+------------------------------------------------+-------+
| Yes  | 2014_10_12_000000_create_users_table           | 1     |
| Yes  | 2014_10_12_100000_create_password_resets_table | 1     |
| Yes  | 2019_08_19_000000_create_failed_jobs_table     | 1     |
| Yes  | 2020_02_05_015307_create_albums_table          | 2     |
| Yes  | 2020_02_05_020352_create_photos_table          | 3     |
+------+------------------------------------------------+-------+
```

### rollback

```bash
php artisan migrate:rollback
+------+------------------------------------------------+-------+
| Ran? | Migration                                      | Batch |
+------+------------------------------------------------+-------+
| Yes  | 2014_10_12_000000_create_users_table           | 1     |
| Yes  | 2014_10_12_100000_create_password_resets_table | 1     |
| Yes  | 2019_08_19_000000_create_failed_jobs_table     | 1     |
| Yes  | 2020_02_05_015307_create_albums_table          | 2     |
| No   | 2020_02_05_020352_create_photos_table          |       |
+------+------------------------------------------------+-------+

#--stepのオプションで[数値]回のロールバックを行います。
php artisan migrate:rollback --step=[数値]
```

### reset

すべてのマイグレーションをロールバックします。

```bash
php artisan migrate:reset
```

### refresh

すべてのマイグレーションをロールバックしてから再びマイグレーションします

```bash
php artisan migrate:refresh
```

### fresh

すべてのテーブルを**ドロップ（削除）**してから再びマイグレーションします。

```bash
php artisan migrate:fresh
```

## キャッシュクリアコマンド

```bash
php artisan cache:clear
php artisan config:clear
php artisan route:clear
php artisan view:clear
```
