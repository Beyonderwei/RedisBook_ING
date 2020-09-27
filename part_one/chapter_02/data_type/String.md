# 字符串（String）

&ensp;&ensp;&ensp;&ensp;字符串是Redis最基础的数据类型，与Memcached的key-value一样，相比较而言，Redis则支持了更多类型的数据和数据的持久化操作。Redis的字符串是二进制安全的，即写入的数据在被读取时不会发生任何变化，因此String可以包含任何数据——数值、字符串或是二进制的图片。字符串所对应的value大小最大为512M（通常我们使用的很小很小）。

&ensp;&ensp;&ensp;&ensp;Redis提供的对String数据类型的操作命令共有25个，这里仅对常用的命令进行介绍，如果读者感兴趣的话可以在Redis官网的命令中筛选出这些命令。

#### 常用命令

##### 设置与获取

SET与GET命令用于添加、设置与获取String类型数据，

- SET key value [EX sec| PX millisec] [NX | XX]

  设置指定key的值，如果key不存在则添加该条数据，存在时则会被覆盖，并且设置的有效期也会被取消。也可以通过EX或PX参数设置过期时间，通过NX或XX参数可在key存在或不存在时对key进行赋值。

  可选参数：

  - EX或PX：设置过期时间，EX单位为秒，PX单位为微秒。
  - NX：仅在该key不存在时存储数据
  - XX：仅在该key已经存在时为key赋值

- MSET key value [key value]

  同时设置多个key的值，与SET命令功能一样，如果不想覆盖已有的值可参考使用MSETNX命令。

- GET key

  获取key对应的值，GET命令仅用于String类型。

- MGET key  [key ...]

  并按顺序获取多个key对应的值，当只有一个key时，相当于GET命令。当某个key不存在或不是String类型时，对应返回的值为nil

##### 数值操作

&ensp;&ensp;&ensp;&ensp;当value的数据可以被解释为一个数值时（如12，1.2），Redis允许对其执行自增、自减等数值操作。Redis并没有表示数值的数据类型，因此数值操作实际上是对字符串进行操作，在返回数据时仍以String类型返回。Redis会对value值进行判断，数值类型的数据在Redis内部依然采用整数或浮点数进行保存，对于整数，最大支持64位有符号的整形，对于浮点数，内部支持的范围为双精度浮点数，但浮点数在返回时输出精度固定为小数点后17位。

&ensp;&ensp;&ensp;&ensp;当被指定的key所对应的value不能被解释为数值时，执行以下操作会返回一个错误；当key不存在或为空串时，value会被设置为0，然后执行对应的数值操作。

- INCR key

  对存储在key的数值加1

- DECR key

  对存储在key的数值减1

- INCRBY key increment

  对存储在key的数值增加 increment

- DECRBY key decrement

  对存储在key的数值减少 decrement

- INCRBYFLOAT key increment

  对存储在key的浮点数增加 increment

##### 字符串操作

- STRLEN key

  获取key所对应字符串的长度，当key对应的value的类型不是string时返回错误。（允许value的值为数值类型，如：value为1.20，则返回长度为4）

- APPEND key value

  将value追加到原来value的后面（当key不存在时创建一个键值对，此时与SET命令功能一致）

- GETRANGE key start end

  获取key对应value的子串，下标从0开始。当下标为负值时表示从结尾开始，最后一个字符所对应的下标为-1，以此类推。

- SETRANGE key offset value

  从key对应字符串的offset处开始，覆盖value长度的字符，key不存在时当作空串处理，key对应字符串的长度小于offset时，空缺位置由0填充。



&ensp;&ensp;&ensp;&ensp;Redis字符串最大是512M，通过SETRANGE和GETRANGE命令，可以将字符串当作线性数组或用来构造想要的数据结构，且访问的时间复杂度仅为O(1)。

