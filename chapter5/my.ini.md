# 创建 MySQL 配置文件

## 最小化配置

```ini
[mysqld]
# GENERAL
datadir = /var/lib/mysql
socket = /var/lib/mysql/mysql.sock
pid-file = /var/lib/mysql/mysql.pid
user = mysql
port = 3306

# INNODB
innodb_buffer_pool_size = <value>
innodb_log_file_size = <value>
innodb_file_per_table = 1
innodb_flush_method = O_DIRECT

# LOGGING
log-error = /var/lib/mysql/mysql-error.log
# 注意：若要启用慢查询，通常还需要设置 slow_query_log = 1
slow_query_log_file = /var/lib/mysql/mysql-slow.log

# OTHER
tmp_table_size = 32M
max_heap_table_size = 32M
max_connections = <value>
thread_cache_size = <value>
table_open_cache = <value>
open_files_limit = 65535

[client]
socket = /var/lib/mysql/mysql.sock
port = 3306
```