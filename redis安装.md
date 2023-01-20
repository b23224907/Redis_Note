# Redis安装





## Ubuntu安装

- apt更新源并安装

```sql
curl -fsSL https://packages.redis.io/gpg | sudo gpg --dearmor -o /usr/share/keyrings/redis-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/redis-archive-keyring.gpg] https://packages.redis.io/deb $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/redis.list

sudo apt-get update
sudo apt-get install redis
```

- 启动redis

```sql
sudo service redis-server start
```

- 连接redis

```c
redis-cli 
127.0.0.1:6379> ping
PONG
```



## 设置密码

### 打开配置文件

```
sudo nano /etc/redis/redis.conf
```

### 修改参数

```
取消该行注释, foobared替换为想要设置的密码
requirepass foobared
```

### 重启redis生效

```
sudo systemctl start redis
```



## 设置外部访问

### 打开配置文件

```
sudo nano /etc/redis/redis.conf
```

### 注释该行

```
#bind 127.0.0.1
```

### 重启redis生效

```
sudo systemctl start redis
```

