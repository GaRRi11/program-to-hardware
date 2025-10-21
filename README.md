## C Program Flow to Assembly

<img width="1049" height="734" alt="c drawio (2)" src="https://github.com/user-attachments/assets/98209edc-5681-4772-9702-b97ae7e9bbb9" />

<pre>  .section .data
g:
    .long 5
 </pre>

.data: initialized data section

g: global variable with value 5 (32-bit integer → 4 bytes)


<pre>  .section .bss
.comm u,4,4
 </pre>

 .bss: uninitialized data section

.comm u,4,4: reserves 4 bytes for variable u, aligned to 4 bytes
→ u is uninitialized global variable

<pre>  .section .rodata
.LC0:
    .string "Hi"
.LC1:
    .float 3.14
 </pre>

 .rodata: read-only constants

.LC0: string constant "Hi"

.LC1: float constant 3.14

<pre>  .text
.globl main
main:
    push rbp
    mov rbp, rsp
    sub rsp, 16
    ...
 </pre>
 
.text: executable code section

## VIRTUAL MEMORY

<img width="500" height="741" alt="virtual memory drawio" src="https://github.com/user-attachments/assets/56b41e6b-39ea-408f-8af1-846ee6e20cbd" />

