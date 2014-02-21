---
layout: post
title: 怎样安装mysql2redis
tagline: Supporting tagline
tags: [mysql2redis, install]
date: 2014-02-21 14:21
comments: true
---

### 简介
[mysql2redis][ref1] 是Mysql的一个UDF(user-defined function)函数,它提供
了mysql与redis之间的数据交互。当mysql的数据进行了更新，它就会调用相应
的trigger一调用mysql2redis里面的函数对redis的数据进行更新。

### 安装前提
安装mysql2redis前，先在系统里安装mysql, redis。

### 依赖

* jemalloc
* apr and apr-util
* hiredis
* lib_mysqludf_json

### 安装过程--Ubuntu
#### 安装jemalloc
安装命令如下:

* sudo apt-get install libjemalloc1 libjemalloc-dev -y

#### 安装apr和apr-util
apr和apr-util是两个依赖包，它们最新版本的下载地址[请点击][ref2]，下载
好的以后，它的安装过程如下(配制，编译，安装):  
install apr

    cd apr-folder
    ./configure
    make
    make test
    sudo make install

install apr-util

    ./configure --with-apr=/usr/local/apr
    make
    sudo make install



#### 安装lib_mysqludf_json
[lib_mysqludf_json][ref4]是一个支持json数据格式的UDF函数,它提供给mysql
与redis进行数据交互。它的下载安装过程如下:

* git clone https://github.com/mysqludf/lib_mysqludf_json.git
* cp lib_mysqludf_json.so /usr/lib/mysql/plugin

#### 安装hiredis
[hiredis][ref3]是redis的一个调用接口，它提供了一些简单的redis的操作,它
的安装和下载过程如下：

* download git clone https://github.com/redis/hiredis.git
* cd hiredis
* make
* sudo make install

#### 安装mysql2redis
[mysql2redis][ref5]的安装和下载过程如下：

* download git clone  https://github.com/aborn/mysql2redis.git
* cd mysql2redis
* make
* sudo make install

### MYSQL的配制
对于lib_mysqludf_json在mysql中执行以下sql命令:

    DROP FUNCTION IF EXISTS json_members;
    DROP FUNCTION IF EXISTS json_array;
    DROP FUNCTION IF EXISTS json_object;
    DROP FUNCTION IF EXISTS json_values;
    CREATE FUNCTION json_members RETURNS STRING SONAME 'lib_mysqludf_json.so';
    CREATE FUNCTION json_array RETURNS STRING SONAME 'lib_mysqludf_json.so';
    CREATE FUNCTION json_object RETURNS STRING SONAME 'lib_mysqludf_json.so';
    CREATE FUNCTION json_values RETURNS STRING SONAME 'lib_mysqludf_json.so';

对于mysql2redis在mysql中执行以下sql命令:

    DROP FUNCTION IF EXISTS json_members;
    DROP FUNCTION IF EXISTS json_array;
    DROP FUNCTION IF EXISTS json_object;
    DROP FUNCTION IF EXISTS json_values;
    CREATE FUNCTION json_members RETURNS STRING SONAME 'lib_mysqludf_json.so';
    CREATE FUNCTION json_array RETURNS STRING SONAME 'lib_mysqludf_json.so';
    CREATE FUNCTION json_object RETURNS STRING SONAME 'lib_mysqludf_json.so';
    CREATE FUNCTION json_values RETURNS STRING SONAME 'lib_mysqludf_json.so';

### [本文完]
在安装过程中遇到的问题，请参照[mysql2redis.md][ref6]

[ref1]: https://github.com/aborn/mysql2redis "mysql2redis"
[ref2]: http://apr.apache.org/download.cgi "apr and apr-utils download"
[ref3]: https://github.com/aborn/mysql2redis "hiredis github project"
[ref4]: https://github.com/mysqludf/lib_mysqludf_json "json udf"
[ref5]: https://github.com/aborn/mysql2redis "mysql2redis"
[ref6]: https://github.com/aborn/popkit/blob/master/doc/mysql2redis.md
"mysql2redis QA"
