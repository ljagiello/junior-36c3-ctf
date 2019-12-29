# Stage 4 - travel - web - easy

## Challenge

Fun climbing up: http://108.61.211.185:8081/

## Solution

The webpage results nginx configuration.

The nginx is misconfigured in `location` section. It does not end with a `/` and as a result of that allows path traversal.

```
http://108.61.211.185:8081/flag../flag
```

## Links
* https://www.acunetix.com/vulnerabilities/web/path-traversal-via-misconfigured-nginx-alias/

## Flag
```
junior-the_easy_way_up
```
