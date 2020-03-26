- ##2. 数据库相关

  &ensp;&ensp;&ensp;&ensp;很多人会有一个误区，因为我们经常说Redis数据库、MySQL数据库等，因此会自然的认为Redis、和MySQL是一个数据库，而实际上他们并不是真正的数据库，他们是DBMS(数据管理系统)，数据库由他们来管理。Redis默认会自动创建16个库，标号从0-15。

  - `select n` 选择当前所使用的库（n：0-15），默认选择的为0号数据库
  - `dbsize` 查看当前该库存储的数据个数
  - `flushdb` 清除当前数据库的所有数据
  - `flushall` 清除所有数据库中的数据

  &ensp;&ensp;&ensp;&ensp;可能你会想这样一个疑问，如何判断我当前正处于哪个数据库呢？不幸的是Redis并没有查询当前所在数据库的命令，细心的你会发现，当你执行如：`select 1` 时发生了如下变化：

  ![](E:\GitHub repositories\RedisBook_ING\part_one\basis_of_redis\images\img-2-2-1.jpg)

  “[]”中的1即当前所在的数据库，而[0]默认是不显示的。