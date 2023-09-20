
# 使用Docker安裝Jenkins

``` sh
到Docker Engine 使用
docker run -p 8080:8080 -p 50000:50000 --restart=on-failure jenkins/jenkins:lts-jdk11

執行docker image 會看到 剛剛下載的 docker image 


```

執行docker container ls 會看到 剛剛啟起來的 container

![](Pasted%20image%2020230920172657.png)

執行docker logs **container的ID** 會看到第一次進去的TOKEN 複製起來

![](Pasted%20image%2020230920172727.png)

url 執行 http://localhost:8080/ 即可看到  Jenkins 登入畫面

![](Pasted%20image%2020230920172740.png)

輸入 剛剛的Token 選擇 她建議的安裝 即可以完成Jenkins 

