# Stage 1 - maybe - rev - medium

## Challenge
Das Blech umdrehen!

## Solution
This is a reverse challenge. First lets see what strings we have in a binary (I will skip not important one):
```
➜  ~ strings chal1-a27148a64d65f6d6fd062a09468c4003
[…]
aber es ist nur noch eine sache von sekunden!
correct!
this_should_totally_be_a_hering_on_a_kuchenblech
wrong!
;*3$"
junior-totally_the_flag_or_maybe_not
[…]
```
With Ghidra we can decompile `chal1-a27148a64d65f6d6fd062a09468c4003`.

It's seems important logic is in `_INIT_1` and `_FINI_1`:

```

char flag[] = "junior-totally_the_flag_or_maybe_not";

void _INIT_1(void)

{
  int i;

  i = 0;
  while (i < 0x24) {
    flag[i] = flag[0x23 - i];
    i = i + 1;
  }
  return;
}
```

```
void _FINI_1(void)

{
  bool correct_flag;
  int i;
  int j;

  i = 0;
  while (i < 0x24) {
    flag[i] = flag[i] ^ s__00301060[i];
    i = i + 1;
  }
  correct_flag = true;
  j = 0;
  while (j < 0x24) {
    if (flag[j] != (&DAT_003010a0)[j * 2 + 1]) {
      correct_flag = false;
    }
    j = j + 1;
  }
  sleep(10);
  puts("aber es ist nur noch eine sache von sekunden!");
  if (correct_flag) {
    puts("correct!");
  }
  return;
}
```
Based on those two functions we can create solution:
```
#include <stdio.h>
#include <stdlib.h>


int main() {
  char flag[] = "junior-totally_the_flag_or_maybe_not";

  unsigned char DAT_003010a0[] = {0x00,0x1e,0x00,0x1a,0x00,0x00,0x00,0x36,0x00,0x0a,0x00,0x10,0x00,0x54,0x00,0x00,0x00,0x01,0x00,0x33,0x00,0x17,0x00,0x1c,0x00,0x00,0x00,0x09,0x00,0x14,0x00,0x1e,0x00,0x39,0x00,0x34,0x00,0x2a,0x00,0x05,0x00,0x04,0x00,0x04,0x00,0x09,0x00,0x3d,0x00,0x03,0x00,0x17,0x00,0x3c,0x00,0x05,0x00,0x3e,0x00,0x14,0x00,0x03,0x00,0x03,0x00,0x36,0x00,0x0f,0x00,0x4e,0x00,0x55,0x00};

  int i = 0;

  for(i=0; i<0x24; i++) {
    flag[i] = flag[0x23 - i];
  }
  for(i=0; i<0x24; i++) {
    flag[i] ^= DAT_003010a0[i * 2 + 1];
  }
  fprintf(stdout, "%s\n", flag);
  return 0;
}
```

## Links
* https://ghidra-sre.org/

## Flag
```
junior-alles_nur_kuchenblech_mafia!!
```
