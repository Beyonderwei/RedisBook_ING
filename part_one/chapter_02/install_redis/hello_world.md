# 第一个Redis“程序”

&ensp;&ensp;&ensp;&ensp;不管我们学习哪一门编程语言，我们接触的第一个程序基本上都是Helloworld，Redis是不是也有属于自己的HelloWorld呢？答案是肯定的（当然HelloWorld只是我给这个测试取的别名而已），通过前面的学习我们知道，Redis相对于其他数据库而言具有极高的性能，而Redis自带的这个HelloWorld程序（redis-benchmark）就是对Redis在本机上进行读写等性能测试，既然都已经安装好了，那么就来看一看Redis在你机器上的性能如何吧！

&ensp;&ensp;&ensp;&ensp;通过不同的安装方式，测试文件所在的路径会有所不同。

## 直接安装

1. 文件位置

   `cd /usr/bin`

2. 直接执行该测试程序

   `redis-bench-mark`

## 通过Docker安装

1. 进入容器

   `docker exec -it 容器ID bash`

2. 文件位置

   `cd /usr/local/bin`

3. 执行测试程序

   `redis-bench-mark`

## 执行结果

&ensp;&ensp;&ensp;&ensp;程序会对很多方面的性能进行测试，这里只截取出SET和GET请求测试结果，可以看出Redis在插入和查询10万条数据的时间仅需1.07秒和1.12秒。服务器的性能越好，当然所需时间越小，作者使用的是阿里云2核2G的服务器进行的测试。

```shell
====== SET ======
  100000 requests completed in 1.07 seconds
  50 parallel clients
  3 bytes payload
  keep alive: 1

99.97% <= 1 milliseconds
100.00% <= 1 milliseconds
93109.87 requests per second

====== GET ======
  100000 requests completed in 1.12 seconds
  50 parallel clients
  3 bytes payload
  keep alive: 1

99.95% <= 1 milliseconds
100.00% <= 1 milliseconds
89126.56 requests per second
```

