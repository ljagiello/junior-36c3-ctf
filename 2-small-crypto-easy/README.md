# Stage 2 - small - crypto - easy

## Challenge
When things are small you have to be carefull! UPDATE: New attachment!
```
message = int('REDACTED', base=35)
N = 31882864753733457706900355195561745936205728163688545344755624355885302677527509480805991969514641856022311950710014654686332759895303124949904557581766107448945073828773339824936328117599459705430379854436444155104737774883908742430619368768337640156577480749932446289330171110268995901030116001751822218657
c = message^3 % N
# c = 272712645051843502864020676686837219546440933810920336253597504130258033336636323130656292878088405243095416128

The message is the flag. No flag format.
```

## Solution
This problem is very similar to RSA with a small exponent, but additionally we have a very large `N`. As a result `mod N` doesn't really do anything and we can just calculate cube root of `c`.
```
➜  ~ python
Python 2.7.17 (default, Oct 24 2019, 12:57:38)
[GCC 4.2.1 Compatible Apple LLVM 11.0.0 (clang-1100.0.33.8)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> c = 272712645051843502864020676686837219546440933810920336253597504130258033336636323130656292878088405243095416128
>>> flag = c**(1./3.)
>>> '{:.0f}'.format(flag)
'6484877229948686425308087880658190336'
```

`6484877229948686425308087880658190336` needs to be converted to base35 to get a flag.


## Links
* https://www.johndcook.com/blog/2019/03/06/rsa-exponent-3/
* https://gchq.github.io/CyberChef/#recipe=To_Base(35)

## Flag
```
juniorissmallkuchenblech
```
