# heyu

Please implement exercise below


Q1
===
Write an simple RESTful API (Using Python Flask or Golang gin)
Employee Data Management
Must have CRUD function
Authentication and validation (plus)
Data format
{
    "id": "<username>",
    "email": "<email>",
    "mobile": "<mobile>",
    "position": {
        "title": "<title>",
        "department": "<department>"
    }
}
  
程式的部份我寫的少，主要還是做系統部份的多<BR>
這題我會上網找一個來抄抄改改，目前粗看會是這個 (因PYTHON相對熟悉)<BR>
https://dev.to/paurakhsharma/flask-rest-api-part-0-setup-basic-crud-api-4650<BR>
然後  我會確認ID重覆是不是有問題 (username不一定是唯一的)<BR>
如果要改可能再加個UID 做為唯一值，或者要把ID+MOBILE做成唯一值<BR>
  <BR>
看貴司的職務說明也應是偏系統，可能的話，我們來聊聊<BR>
- 監控
- 高可用
- 系統管理等等等<BR>
如果是我誤會了，這職務要寫很多的CODE，那我放棄<BR>
  
Q2
===
Build your application to container images and manage your service with docker-compose
Dockerfile
docker-compose.yml

這題應是承接上面<BR>
所以他解題是下一個BASE IMAGE，然後把 環境佈好，把FLASK 與API CODE丟上去跑<BR> 
用dockerfile寫成固定的設定檔，變成一個自訂的IMAGE<BR>
https://medium.com/bb-tutorials-and-thoughts/how-to-dockerize-the-python-rest-api-with-flask-library-d2b51dd4a0ae<BR>
粗粗看我會抄這個來改  (之所以是粗粗看，是系統建置過程中，先求有，再求好，也許未來我會改架構以優化或符合新需求)<BR>
並在dockerfile中加一段動作 git clone / pull Q1的程式碼<BR>
PS下，這段做出來的image我會給他專案名稱加功能的關鍵字在其中，因為很多專案很多IMAGE時，要確認人員的動作正確，會需要一些管理的功夫，命名就是其中一環<BR>
<BR>

再用dockecompose寫成固定的設定檔<BR>
https://docs.docker.com/compose/gettingstarted/<BR>
一樣找一個來抄抄改改<BR>
再看怎啟程式 docker compose up -d (可能寫 init.d rc.local  or systemd ，在規範上 我定義程式的啟用一定要在開機時能自動運行，這樣基本有2個好處，1是不會忘記這台是跑什麼的東東，跑很多時也不會缺漏或錯置，2是可能供一線人員放大絕，在服務異常處理不行時，可以重啟機器)<BR>


Q3
===
Upload your git repository to public github and must have content below
app                   # application location
.env.example
Dockerfile
docker-compose.yml
README.md             # How to use
Note
We will clone your git repository and verify in local dev environment
<BR>
我沒有CODE，只有思維如上所述，如果不合適，我很抱歉<BR>
