# 通过Docker安装Redis

&ensp;&ensp;&ensp;&ensp;Docker作为一个开源的应用容器引擎，解决了运行环境和配置等问题而被广泛使用，默认读者已经完成了Docker的安装，下面介绍在已经安装了Docker后，通过它来安装Redis。

1. 在Docker仓库中搜索Redis

   `docker search redis`

2. 下载镜像

   `docker pull 镜像名`

3. 本地新建配置文件，手动到Github的Redis仓库中找到配置文件并将内容复制进来

   `vim /myredis/conf/redis.conf`

4. 启动容器

   `docker run -p 6379:6379 --name myredis -v /myredis/conf/redis.conf:/usr/local/etc/redis/redis.conf -d redis redis-server /usr/local/etc/redis/redis.conf --port 6379`
   
5. 进入容器并开启一个客户端连接redis

   `docker exec -it 容器ID redis-cli`

6. 乒乓测试：

   `ping`    返回 “PONG”

7. 退出Redis或容器

   `exit`



**注意事项：**

1. 在下载镜像时，可以直接选择Stars最多名为redis的这一个，其版本在5.0以上。
2. 由于Docker中的Redis镜像中没有配置文件，因此采用了本地创建，通过数据卷映射的方式。