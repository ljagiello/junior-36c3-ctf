# Stage 1 - tracer - for - easy

## Challenge
Tracing the Kuchenblech-Mafia is hard!

[Attachment](https://github.com/ljagiello/junior-36c3-ctf/blob/master/1-tracer-for-easy/chal2-98f6917950f95448890949f2d9b9850a)

## Solution
In attachment we see a strace output where flag was saved in vim.

Interesting part is:
```
✗ cat chal2-98f6917950f95448890949f2d9b9850a | grep read
[…]
541   read(0, "i", 4096)                = 1
541   read(0, "j", 4096)                = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "u", 4096)                = 1
541   read(0, "n", 4096)                = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "i", 4096)                = 1
541   read(0, "o", 4096)                = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "r", 4096)                = 1
541   read(0, "-", 4096)                = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "n", 4096)                = 1
541   read(0, "a", 4096)                = 1
541   read(0, "\33", 4096)              = 1
541   read(0, "y", 4096)                = 1
541   read(0, "y", 4096)                = 1
541   read(0, "p", 4096)                = 1
541   read(0, "A", 4096)                = 1
541   read(0, "\177", 4096)             = 1
541   read(0, "o", 4096)                = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "i", 4096)                = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "s", 4096)                = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "w", 4096)                = 1
541   read(0, "a", 4096)                = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "y", 4096)                = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "b", 4096)                = 1
541   read(0, "e", 4096)                = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "t", 4096)                = 1
541   read(0, "t", 4096)                = 1
541   read(0, "e", 4096)                = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "r", 4096)                = 1
541   read(0, "!", 4096)                = 1
541   read(0, "\33", 4096)              = 1
541   read(0, "g", 4096)                = 1
541   read(0, "g", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "J", 4096)                = 1
541   read(0, "b", 4096)                = 1
541   read(0, "b", 4096)                = 1
541   read(0, "~", 4096)                = 1
541   read(0, "~", 4096)                = 1
541   read(0, "~", 4096)                = 1
541   read(0, "~", 4096)                = 1
541   read(0, "~", 4096)                = 1
541   read(0, "~", 4096)                = 1
541   read(0, "~", 4096)                = 1
541   read(0, "~", 4096)                = 1
541   read(0, "\33", 4096)              = 1
541   read(0, ":", 4096)                = 1
541   read(0, "s", 4096)                = 1
541   read(0, "/", 4096)                = 1
541   read(0, " ", 4096)                = 1
541   read(0, "/", 4096)                = 1
541   read(0, "/", 4096)                = 1
541   read(0, "g", 4096)                = 1
541   read(0, "\r", 4096)               = 1
541   read(0, "\33", 4096)              = 1
541   read(0, ":", 4096)                = 1
541   read(0, "w", 4096)                = 1
541   read(0, "q", 4096)                = 1
541   read(0, "\r", 4096)               = 1
```

Besides regular characters we have some special characters:
```
\r - ENTER
\33 - ESC
\177 - DEL
```
After retyping it in vim, we have a flag.

## Links
* http://www.robelle.com/smugbook/ascii.html

## Flag
```
junior-nanoiswayBETTER!
```
