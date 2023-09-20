![[Pasted image 20230920162511.png]]


進入Jenkins 左上角有一個 Newitem 點選 Freestyle project 

下一步後 這邊輸入專案git網址
![[Pasted image 20230920163408.png]]

勾選
![[Pasted image 20230920163515.png]]

收到git請求 會發出的訊息 ( 隨便輸入即可.只是測試有沒有收到)
![[Pasted image 20230920163538.png]]

下載ngrok 解壓縮到資料夾 執行cmd 
輸入 ngrok http http://localhost:8080/  即可得到

![[Pasted image 20230920164625.png]]

在瀏覽器 貼上  即可以看到 Jenkins畫面


在專案的Settings Webhooks 設定 Payload URL

輸入上面的網址 記得要加上/github-webhook/

![[Pasted image 20230920164954.png]]

更新一筆專案內容 push 上去 

回到Jenkins 即可看到 Build 有一筆新的


![[Pasted image 20230920165328.png]]

點選進去  即可看到 剛剛輸入的文字  代表成功
![[Pasted image 20230920165535.png]]