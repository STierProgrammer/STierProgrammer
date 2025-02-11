# STierProgrammer 
```c
#include <stdio.h>

int main() {
    printf("Hello, I am STierProgrammer!");

    return 0;
}
```

## ⚡ GitHub Stats

<p align="center">
    <img height="120px" src="https://github-readme-stats.vercel.app/api?username=STierProgrammer&hide_title=true&hide_border=true&show_icons=true&include_all_commits=true&count_private=true&line_height=21&hide_rank=true&icon_color=fa8b00&theme=dark" />
    <img height="120px" src="https://github-readme-stats.vercel.app/api/top-langs/?username=STierProgrammer&hide=html&hide_title=true&hide_border=true&layout=compact&langs_count=8&theme=dark" />
</p>


```asm
section .data
    content db "STierProgrammer!", 0Ah 
    len equ $-content

section .bss
    hStdOut resq 1

section .text
    global main
    extern GetStdHandle, WriteConsoleA, ExitProcess
    extern kernel32.dll 

main:
    sub rsp, 32
    mov ecx, -11 
    call GetStdHandle

    mov qword [rel hStdOut], rax 

    mov rcx, qword [rel hStdOut] 
    lea rdx, [rel content]
    mov r8, len
    lea r9, [rsp-8] 
    call WriteConsoleA

    xor ecx, ecx
    call ExitProcess
```
