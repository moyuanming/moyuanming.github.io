---
layout: post
title: 怎样安装mysql2redis
tagline: Supporting tagline
tags: [mysql2redis, install]
date: 2014-02-21 14:21
comments: true
---
{% include JB/setup %}

### 简介
[mysql2redis][ref1] 是Mysql的一个UDF(user-defined function)函数,它提供
了mysql与redis之间的数据交互。当mysql的数据进行了更新，它就会调用相应
的trigger一调用mysql2redis里面的函数对redis的数据进行更新。

### 安装前提
安装mysql2redis前，先在系统里安装mysql, redis。

### 依赖
1. jemalloc
2. apr and apr-util
3. hiredis
4. lib_mysqludf_json

### 安装过程--Ubuntu
#### 安装jemalloc
安装命令如下:  
> sudo apt-get install libjemalloc1 libjemalloc-dev -y  

#### 安装apr和apr-util
apr和apr-util是两个依赖包，它们最新版本的下载地址[请点击][ref2]，下载
好的以后，它的安装过程如下(配制，编译，安装)：

* install apr
  1. cd apr-folder
  2. ./configure
  3. make
  4. make test
  5. sudo make install
* install apr-util
  1.  ./configure --with-apr=/usr/local/apr
  2. make
  3. sudo make install
  
[ref1]: https://github.com/aborn/mysql2redis "mysql2redis"
[ref2]: http://apr.apache.org/download.cgi "apr and apr-utils download"


