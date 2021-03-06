# MySQL

### **MySQL管理**

**关闭开启服务**

```
ps -ef | grep mysqld # 检查MySQL服务是否启动
/usr/bin/mysqld_safe & # 启动MySQL服务器
/usr/bin/mysqladmin -u root -p shutdown # 关闭MySQL服务器
```

**用户设置**

```
use mysql;
INSTER INTO user
(
host,user,password,select_priv,insert_priv,update_priv
)
VALUES
(
'localhost','test',PASSWORD('test'),'Y','Y','Y'
);
FLUSH PRIVILEGES; # 重载授权表
SELECT host,user,password FROM user WHERE user='test';
```

> 注意:MySQL5.7中表user表的password换成**authentication\_string.**
> 
> select\_priv,insert\_priv,update\_priv为用户的权限.

```
GRANT SELECT,INSERT,UPDATE,DELETE,CREATE,DROP
->ON TUTORIALS.*
->TO 'guest'@'localhsot'
->IDENTIFIED BY 'guest';
```

**管理命令**

```
use 数据库名; # 切换数据库
SHOW DATABASES; # 显示数据库列表
SHOW TABLES; # 显示数据表列表
SHOW COLUMNS FROM 数据表; # 显示字段属性默认值等
SHOW INDEX FROM 数据表; # 显示数据表的详细索引信息,包括主键
SHOW TABLE STATUS FROM db_name [LIKE 'pattern']\G;
# 输出MySQL数据库管理系统的性能及统计信息
SHOW TABLE STATUS FROM 数据库; # 显示所有表信息
SHOW TABLE STATUS FROM 数据库 LIKE 'emr_%'; # 表名emr_开头的
# \G按列打印
```

**创建数据库**

```
mysqladmin -u root -p create test1 # 创建数据库
CREATE DATABASE test # 创建数据库
```

**删除数据库**

```
mysqladmin -u root -p drop test1
DROP DATABASE test # 删除数据库
```

**选择数据库**

```
use mysql; # 选择数据库
```

**创建数据表**

```
use test;
CREATE TABLE test (
    ->id INT NOT NULL AUTO_INCREMENT,
    ->title VARCHAR(100) NOT NULL,
    ->author VARACHAR(40) NOT NULL,
    ->date DATE,
    ->PRIMARY KEY(id)
);
```

**删除数据表**

```
DROP TABLE test;
```

插入数据



查询数据





