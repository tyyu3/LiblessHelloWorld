# LiblessHelloWorld

LiblessHelloWorld is a C+ASM project to write "Hello World!" without using libc.

## Buld instructions

I used gcc:

```bash
gcc -nostdlib -no-pie -o hello main.c start.S hello.S
```
*-nostdlib* stops gcc from autoincuding libc

*-no-pie* is apperently needed because of defining custom .data section to avoid segfault, but I'm not sure

## Contents

| File  | Description |
| ------------- | ------------- |
| start.S  | calls main() on program start |
| main.c  | main() is called from _start() and calls hello() |
| hello.S  | writes "Hello world!" to terminal |

## Reference
I used this blogpost as a reference:
https://blogs.oracle.com/linux/hello-from-a-libc-free-world-part-1-v2
