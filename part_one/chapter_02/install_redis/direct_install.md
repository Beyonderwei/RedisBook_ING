# 直接安装

&ensp;&ensp;&ensp;&ensp;直接安装的方式相对简单，但是会由于所使用的Linux系统的发行版本不同，导致安装的redis版本相对较旧，以Ubuntu为例，如果按此方式安装版本低于本书所讲的5.0，则会导致一少部分命令无法执行。如果你是初学者，那么推荐此方式，如果你已有Docker的使用经历，那么更推荐通过Docker安装指定版本（当然读者也可通过去官网或Github下载指定版本解压、编译并安装）。

&ensp;&ensp;&ensp;&ensp;直接安装会用到的命令如下，读者可在终端中按需执行。

1. 更新apt：

   `apt-get update` 

2. 安装Redis: 

   `sudo apt-get install redis-server`

3. 默认的安装位置：

   `cd /usr/bin` 

4. 卸载已经安装的Redis：

   `sudo apt-get purge --auto-remove redis-server` 

5. 查看安装的redis版本：

   `redis-server --version`

6. 启动redis：

   `redis-server /etc/redis/redis.conf` 

7. 查看Redis是否启动：

   `ps aux|grep redis`

8. 关闭在运行的Redis

   `sudo /etc/init.d/redis-server stop`

9. 启动一个客户端，并连接到Redis服务器：

   `redis-cli -p 6379` 

10. 乒乓测试：

    `ping`    返回 “PONG”

11. 退出连接的客户端：

    `exit`



&ensp;&ensp;&ensp;&ensp;依次执行以上第1、2、6、9条命令即可安装成功并连接到Redis服务器，注意在第六步启动Redis时指定了redis.conf配置文件，即按照该配置文件启动Redis，该文件是安装Redis时自带的配置文件，后面会详细讲解。如果乒乓测试正常，则说明Redis已经成功安装。运行效果如下：

```shell
root@xxx:~# redis-server /etc/redis/redis.conf
root@xxx:~# redis-cli -p 6379
127.0.0.1:6379> ping
PONG
127.0.0.1:6379>
```