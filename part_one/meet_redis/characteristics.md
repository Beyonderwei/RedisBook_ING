# 特点

&ensp;&ensp;&ensp;&ensp;知道了什么是Redis，下面就来看一下它都具有什么样的特点，正是因为Redis在这些方面所具有的优良表现，才让Redis如此的成功。

- 开源：

  &ensp;&ensp;&ensp;&ensp;为什么说开源如此的重要呢？因为开源意味着免费的使用，为什么会有去IOE，这里的“O”指的就是Oracle数据库，因为使用Oracle是需要付费的，像阿里等这样的大公司在之前就需要向Oracle公司交付大量的费用，小公司当然更加承受不起这样的费用，因此会更多的使用开源的数据库。同时开源大大促进了互联网软件的发展。

- 多种语言开发：

  &ensp;&ensp;&ensp;&ensp;支持包括C、C++、Go、Java、JavaScript、Lua、Object-C、PHP、Python、Rust、Swift等

- 多种数据类型：

  - 字符串（String）String是Redis最基本的数据类型。
  - 列表（Lists）List是按照插入顺序排序的字符串列表。
  - 集合（Sets）Sets即无序的字符串集合。
  - 哈希（Hashes）用来表示对象的一种数据类型。
  - 有序集合（Sorted sets）非重复元素的集合，集合元素按照评分机制排序。

- 数据持久化：

  &ensp;&ensp;&ensp;&ensp;由于内存中的内容会掉电消失，Redis提供了两种数据持久化的方式：快照和日志。

- 主从复制：

  &ensp;&ensp;&ensp;&ensp;为了减轻数据库的查询压力以及容灾恢复，Redis的数据库可以复制任意数量的副本，如树形图一样。

- 高性能：

  &ensp;&ensp;&ensp;&ensp;由于Redis的很多操作都是存粹的内存操作，加上特殊设计的数据结构，降低了很多操作的时间复杂度，使得它具有极高的性能。
  

  

  

  

  

  

  

  