Redis服务

redis简介

Redis 是完全开源免费的，遵守BSD协议，是一个高性能的key-value数据库。

在公司应用中将他设置为高速缓存，提高用户访问速度，降低mysql数据库的只读压力。

redis安装搭建以及常用命令

下载官网redis安装包
```
make 
make PREFIX=/usr/local/redis install
```

因为没有配置文件，所以将解压目录中的配置文件复制过来

```
cp redis/redis.conf /usr/local/redis
```

打开配置文件，启动后台启动选项
``
daemonize yes
```
然后启动服务端，指定配置文件就可以了
```
./bin/redis-server redis.conf
```
启动客户端操作
```
./bin/redis-cli redis.conf
```


常用命令
keys *  			    查看所有键
exists key　　　　　　　　　　　　  测试指定key是否存在
del key1 key2….keyN　　　　　　　 　删除指定key
type key　　　　　　　　　　　　　　返回指定key的value类型
keys pattern　　　　　　　　　　　　返回指定模式的所有key
rename oldkey newkey　　　　　　　  改名字
dbsize　　　　　　　　　　　　　　　返回当前数据路的key数量
expire key seconds　　　　　　　　　为key指定过期时间
ttl key　　　　　　　　　　　　 　　返回key的过期剩余秒数
select db-index　　　　　　　 　　　选择数据库
move key db-index　　　　　　　　　 把key从当前数据库移动到指定数据库
flushdb　　　　　　　　　　　　　 　删除当前数据库所有key
flushall　　　　　　　　　　　　　　删除所有数据库中的所有key


redis 配置密码

打开主配置文件中
```
requirepass 123456
```
或者登入时，输入密码

auth 123456


