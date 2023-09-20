![](pic/Pasted%20image%2020230920172752.png)


進入Jenkins 左上角有一個 Newitem 點選 Freestyle project 

下一步後 這邊輸入專案git網址
![](pic/Pasted%20image%2020230920172803.png)

勾選
![](pic/Pasted%20image%2020230920172815.png)

收到git請求 會發出的訊息 ( 隨便輸入即可.只是測試有沒有收到)
![](pic/Pasted%20image%2020230920172824.png)

下載ngrok 解壓縮到資料夾 執行cmd 
輸入 ngrok http http://localhost:8080/  即可得到

![](pic/Pasted%20image%2020230920172835.png)

在瀏覽器 貼上  即可以看到 Jenkins畫面


在專案的Settings Webhooks 設定 Payload URL

輸入上面的網址 記得要加上/github-webhook/

![](pic/Pasted%20image%2020230920172846.png)

更新一筆專案內容 push 上去 

回到Jenkins 即可看到 Build 有一筆新的
![](pic/Pasted%20image%2020230920172900.png)

點選進去  即可看到 剛剛輸入的文字  代表成功
![](pic/Pasted%20image%2020230920172911.png)