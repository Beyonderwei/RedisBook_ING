# 命令基础

&ensp;&ensp;&ensp;&ensp;Redis的命令共200多个，直接罗列出所有的命令逐个讲解不但让人觉得无聊，也不容易记住，因此这里主要介绍一些我们常用的基础命令，而其他的命令我们将在后面的使用中再逐个说明，如果在实际使用中忘记了哪个命令的使用方法，也可以到Redis官网中的命令中心去查询，在那里官方把所有的命令按照字母顺序排列，因此你可以快速检索。下面我们就来讲解一些常用的基础命令。

## 1. Redis相关

&ensp;&ensp;&ensp;&ensp;Redis是基于客户端/服务器（C/S）的数据库管理系统（DBMS），而我们后端的代码在访问Redis的时候也是一个客户端的角色，因此我们在后端测试的的时候是需要一个客户端去访问的。

- `redis-cli` 启动一个客户端，并连接到本地服务器
- `ping` 返回PANG 表示Redis运行成功

##2. 数据库相关

&ensp;&ensp;&ensp;&ensp;很多人会有一个误区，因为我们经常说Redis数据库、MySQL数据库等，因此会自然的认为Redis、和MySQL是一个数据库，而实际上他们并不是真正的数据库，他们是DBMS(数据管理系统)，数据库由他们来管理。Redis默认会自动创建16个库，标号从0-15。

- `select n` 选择当前所使用的库（n：0-15），默认选择的为0号数据库
- `dbsize` 查看当前该库存储的数据个数
- `flushdb` 清除当前数据库的所有数据
- `flushall` 清除所有数据库中的数据

&ensp;&ensp;&ensp;&ensp;可能你会想这样一个疑问，如何判断我当前正处于哪个数据库呢？不幸的是Redis并没有查询当前所在数据库的命令，细心的你会发现，当你执行如：`select 1` 时发生了如下变化：

![](E:\GitHub repositories\RedisBook_ING\part_one\basis_of_redis\images\img-2-2-1.jpg)

“[]”中的1即当前所在的数据库，而[0]默认是不显示的。

 ## 3. 常用数据指令

- `set key value` 存储key-value到数据库
- `setnx key value` 当key不存在时才存储数据，setnx（set if not exist）
- `setex key sec value` 存储key-value到数据库,并设置该数据的有效期为sec秒。
- `mset k1 v1 k2 v2` 一次存储多个数据
- `del key` 删除key
- `move key n` 将该键值对移动到其他库（n为数据库编号）
- `get key` 查询key所对应的值
- `mget key1 key2` 一次查询多个key的值
- `keys *` 查询当前库的所有key
- `exists key` 查看某个key是否存在
- `type key` 查看key对应数据的类型
- `expire key sec` 设置key的有效期（sec为秒钟）
- `ttl key` 查看数据还有多久过期（-1：长期有效，-2：过期）