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

