---
description: データベースコンテーなーの基本構築、及び、C:\workspace\Docker\MySQLフォルダーをマウントする。
---

# MySQL

```bash
// Some code
docker pull mysql
docker run -it --name dev-mysql -P --expose=3306 -p 3306:3306 -v C:\workspace\Docker\MySQL:/mnt -e MYSQL_ROOT_PASSWORD=password -d mysql:latest
docker exec -it dev-mysql bash

mysql -u root -p -h 127.0.0.1

use mysql;

CREATE USER 'clubnets'@'%' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON * . * TO 'clubnets'@'%';

ALTER TABLE mst_shop DROP COLUMN alert_flag;
ALTER TABLE mst_shop ADD alert_flag smallint(1) NULL AFTER data_type;
ALTER TABLE `mst_shop` ADD `alert_flag` SMALLINT(1) NULL DEFAULT '0' AFTER `data_type`;

docker run -it --name dev-mysql -P --expose=3306 -p 3306:3306 -e MYSQL_ROOT_PASSWORD=password -d mysql:latest
```
