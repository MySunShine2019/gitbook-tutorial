# 创建数据库

***基本语法：***

​	`create database databasename [库选项];`

**库选项**

* 字符集（`charset`）

> `create database databasename charset gbk;`

* 校对集（`collate`）

# 查看数据库

**显示全部**

> `show databases;`

**显示部分（通过模糊查询关键字like）**

1. **%代表多个字符**
2. **_代表单个字符**

> `show databases like 'my%';`
>
> `show databases like '_my';`

# 选择/使用数据库

**基本语法：**

> `use databasename;`

# 修改数据库

**修改数据库的库选项（字符集和校对集）**

> 基本语法:
>
> `alter database databasename charset gbk;`
>
> or  `alter database databasename charset = gbk;`

#  删除数据库

> 基本语法：
>
> `drop database databasename;`

# 查看数据库创建语句

> 基本语法：
>
> `show create database databasename;`



# 插入数据为什么不能插入中文？

**`mysql> insert into teacher values('张帆',12);
  ERROR 1366 (HY000): Incorrect string value: '\xD5\xC5\xB7\xAB' for column 'name' at row 1`**

* ***解决办法：***

> 修改`mysql`客服端`mysql.exe`与服务端`mysqld.exe`的字符集
>
> > **查看数据库客服端和服端端所使用的字符集**
> >
> > `show variables like 'character_set_%';`
> >
> > * ` set names gbk;`
> >
> > *  ` set  character_set_client = gbk;`
> >
> > * `set character_set_results = gbk;`
>
> 如果只修改了`character_set_client`变量的值没有修改`character_set_results`的值那么插入的数据会出现乱码





