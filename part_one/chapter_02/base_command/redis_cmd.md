## 1. Redis相关

&ensp;&ensp;&ensp;&ensp;Redis是基于客户端/服务器（C/S）的数据库管理系统（DBMS），而我们后端的代码在访问Redis的时候也是一个客户端的角色，因此我们在后端测试的的时候是需要一个客户端去访问的。

- `redis-cli` 启动一个客户端，并连接到本地服务器
- `ping` 返回PANG 表示Redis运行成功