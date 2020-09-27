# Table of contents

* [RedisBook\_ING](README.md)
* [作者序](foreword/README.md)
  * [起因](foreword/reason.md)
  * [内容简介](foreword/abstract.md)
  * [本书特点](foreword/characteristics.md)
  * [本书的读者对象](foreword/target_reader.md)
  * [致谢](foreword/acknowledgements.md)
* [上篇](part_one/README.md)
  * [一、初识Redis](part_one/chapter_01/README.md)
    * [1.1 NoSQL](part_one/chapter_01/NoSQL/README.md)
      * [1.1.1 NoSQL 简介](part_one/chapter_01/NoSQL/brief_introduction.md)
      * [1.1.2 与关系型数据库的对比](part_one/chapter_01/1.1 NoSQL/compare_with_rds.md)
    * [1.2 发展](part_one/chapter_01/development_of_redis.md)
    * [1.3 概念](part_one/chapter_01/concept.md)
    * [1.4 特点](part_one/chapter_01/characteristics.md)
    * [1.5 用途](part_one/chapter_01/usage_scenarios.md)
  * [二、Redis基础](part_one/basis_of_redis/README.md)
    * [2.1 安装Redis](part_one/chapter_02/install_redis/README.md)
      * [2.1.1 直接安装](part_one/chapter_02/install_redis/direct_install.md)
      * [2.1.2 通过Docker安装](part_one/chapter_02/install_redis/install_by_docker.md)
      * [2.1.3 第一个Redis程序](part_one/chapter_02/install_redis/hello_world.md)
    * [2.2 命令基础](part_one/chapter_02/base_command/README.md)
      * [2.2.1 Redis相关](part_one/chapter_02/base_command/redis_cmd.md)
      * [2.2.2 数据库相关](part_one/chapter_02/base_command/database_cmd.md)
      * [2.2.3 常用数据指令](part_one/chapter_02/base_command/regular_cmd.md)
    * [2.3 数据类型](part_one/chapter_02/data_type/README.md)
      * [2.3.1 字符串(String)](part_one/chapter_02/data_type/String.md)
      * [2.3.2 列表(Lists)](part_one/chapter_02/data_type/Lists.md)
      * 2.3.3 哈希(Hashes)
      * 2.3.4 集合(Sets)
      * 2.3.5 有序集合(Sorted Sets)
    * [2.4 批量插入数据](part_one/basis_of_redis/bulk_insert.md)
  * [三、配置文件](part_one/configuration_file/README.md)
    * [3.1 配置文件介绍](part_one/configuration_file/pei-zhi-wen-jian-jie-shao.md)
    * [3.2 配置文件详解](part_one/configuration_file/pei-zhi-wen-jian-xiang-jie.md)
      * 3.2.1 网络配置
      * 3.2.2 通用配置
      * 3.2.3 快照配置
      * 3.2.4 安全配置
      * 3.2.5 其他常用配置
  * [四、数据持久化](part_one/data_persistence/README.md)
    * [4.1 RDB](part_one/data_persistence/rdb.md)
      * 4.1.1 持久化原理
      * 4.1.2 配置方法
      * 4.1.3 试用场景
      * 4.1.4 优缺点
    * [4.2 AOF](part_one/data_persistence/aof.md)
      * 4.2.1 持久化原理
      * 4.2.2 配置方法
      * 4.2.3 试用场景
      * 4.2.4 优缺点
    * 4.3 两种数据持久化的对比与选择
  * [五、主从复制、读写分离](part_one/master-slave_copy+read_and_write_separation/README.md)
    * [5.1 一主多从模式](part_one/master-slave_copy+read_and_write_separation/yi-zhu-duo-cong-mo-shi.md)
      * 5.1.1 原理介绍
      * 5.1.2 配置方法
      * 5.1.3 特点分析
    * [5.2 去中心化](part_one/master-slave_copy+read_and_write_separation/qu-zhong-xin-hua.md)
      * 5.2.1 原理介绍
      * 5.2.2 配置方式
      * 5.2.3 特点分析
    * [5.3 从机变为主机](part_one/master-slave_copy+read_and_write_separation/cong-ji-bian-wei-zhu-ji.md)
      * 5.3.1 原理介绍
      * 5.3.2 配置方式
      * 5.3.3 特点分析
    * 5.4 三种模式的对比分析
  * [六、数据安全与数据加密](part_one/security_and_encryption/README.md)
    * [6.1 安全模式](part_one/security_and_encryption/an-quan-mo-shi.md)
      * 6.1.1 常规模式
      * 6.1.2 访问认证
      * 6.1.3 代码层面的安全
      * 6.1.4 常见攻击方式
    * [6.2 网络安全](part_one/security_and_encryption/wang-luo-an-quan.md)
  * [七、Redis高级](part_one/senior/README.md)
    * [7.1 管道与事务](part_one/senior/guan-dao-yu-shi-wu.md)
      * Redis管道
      * Redis事务
    * [7.2 Redis数据分区](part_one/senior/redis-shu-ju-fen-qu.md)
      * 7.2.1 分区简介
      * 7.2.2 实现数据分区
      * 7.2.3 优缺点分析
    * [7.3 分布式锁](part_one/senior/fen-bu-shi-suo.md)
    * [7.4 发布/订阅与事件通知](part_one/senior/fa-bu-ding-yue-yu-shi-jian-tong-zhi.md)
    * [7.5 处理Redis信号](part_one/senior/chu-li-redis-xin-hao.md)
    * [7.6 Redis客户端连接](part_one/senior/redis-ke-hu-duan-lian-jie.md)
    * [7.7 高可用Redis](part_one/senior/gao-ke-yong-redis.md)
* [下篇](xia-pian.md)
* [附录](fu-lu.md)

