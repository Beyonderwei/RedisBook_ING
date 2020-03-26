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