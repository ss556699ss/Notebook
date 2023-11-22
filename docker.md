
## 命令

列出所有容器
```sh
sudo docker ps -a
```



run  image

start container

## Sql server 的Dockerfile 

# 使用 SQL Server 2019 的基础镜像
```
FROM mcr.microsoft.com/mssql/server:latest (從dockerhub抓取下來)
```
# 設置環境變數
```sh
ENV ACCEPT_EULA=Y
ENV SA_PASSWORD=1qaz@WSX\#EDC\!
```

# 將SQL腳本複製到容器中
```
COPY MsSql.sql /usr/src/app/
WORKDIR /usr/src/app/
```

```
RUN (/opt/mssql/bin/sqlservr --accept-eula & ) | grep -q "Service Broker manager has started" &&  /opt/mssql-tools/bin/sqlcmd -S127.0.0.1 -USA -P1qaz@WSX\#EDC\! -i MsSql.sql
```
# 在啟動容器時運行SQL Server
```
CMD ["/opt/mssql/bin/sqlservr"]
```

# 登入到 Harbor

```
docker login 10.250.75.140(Harbor Ip)
```

# **標記容器映像**

```
在上傳之前，你需要使用 `docker tag` 命令將容器映像標記為目標 Harbor 位置

`docker tag my-sql-server-image 10.250.75.140/asher/my-image:latest`

這裡的 `my-image:latest` 是你的本地容器映像，`myharbor.example.com` 是你的 Harbor 地址，`my-project` 是你的項目名稱。
```

# **推送容器映像**

```
`docker push 10.250.75.140/asher/my-sql-server-image`
```

# build 成 images

`docker build -t <IMAGE_NAME>:<TAG> .`

docker images 產生 container 
```
docker run -d -p 127.0.0.1:1433:1433 --name sql_server_container --restart always 809f8a237296

```

docker 原理 
![](pic/Pasted%20image%2020231019094534.png)

![](pic/Pasted%20image%2020231019111324.png)