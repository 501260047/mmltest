# Redis
## edis简介：<br>
　　Redis 是一个高性能的开源的、C语言写的Nosql（非关系型数据库），数据保存在内存中。Redis 是以key-value形式存储，和传统的关系型数据库不一样。不一定遵循传统数据库的一些基本要求，比如说，不遵循sql标准，事务，表结构等等，Redis严格上不是一种数据库，应该是一种数据结构化存储方法的集合。
## 特点：<br>
①数据存储：Redis不仅可以存储在内存中，还能持久化。存取速度快，并发能力强，安全性高。<br>
②支持类型：支持的类型相较于memcached更多。<br>
③语言支持：支持多种语言。<br>
④是否集群：支持集群。<br>
## 使用场景：<br>
1.缓存　经常查询数据，放到读速度很快的空间(内存)，以便下次访问减少时间。减轻压力，减少访问时间.而redis就是存放在内存中的。<br>
2.计数器应用　网站通常需要统计注册用户数，网站总浏览次数。<br>
3.设定有效期的应用　设定一个数据，到一定的时间失效。 自动解锁，如购物券。<br>
## 安装（略）<br>
## 连接redis进行基本操作：<br>
### 连接：
cmd>{%redis%}/redis-cli -h ip地址 -p 端口号　　ip 默认为本地 -p 默认6379 <br>
### 简单操作：<br>
```
set name"hello,redis"　　get name　单一的设置获取
mset name mml age 18     mget name age 同时设置/获取一个或多个 key-value 对
keys *  //获取所有key列表
del key  //删除key
expire key xx //设置key的过期时间(xx秒后过期)
ttl key //查看key的过期时间
flushall //清空整个redis服务器数据，所有的数据库全部清空
flushdb  //清除当前库，redis中默认有16个数据库，名称分别为0,1,2.。。15

```
### Java用jedis操作redis：<br>
```
Jedis jedis = new jedis(ip地址);
jedis.set("name","mml");
关闭连接
jedis.close();
```
