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


Virtual memory is created and managed by the OS, combining physical RAM and disk storage. When RAM is full, inactive pages are moved to disk (swap), allowing programs to run as if they have more memory than physically available. Only kernel code, drivers, or embedded programs can access physical RAM directly.

Each section has specific permissions to prevent malicious writes and enforce isolation, security, and convenience. Each process sees its own virtual address space, divided into sections: 

Stack: Grows downwards; stores function call frames, local variables, and return addresses. Follows LIFO principle. 

Heap: Grows upwards; stores dynamically allocated memory (malloc/new). Allocation/frees are arbitrary order. 

BSS (Block Started by Symbol): Uninitialized global/static variables. Zeroed at program start. 

Data Segment: Initialized global/static variables. 

Text / Code Segment: Program instructions and read-only constants. 

Kernel Space: Reserved for OS, inaccessible to user processes. 

## C PROGRAM VIRTUAL MEMORY 

<img width="996" height="801" alt="c-vm drawio" src="https://github.com/user-attachments/assets/22604d36-ff41-42a5-b379-a56cebb4053d" />

Whenever a function is called, a new stack frame is created, and the old EIP address gets pushed to the top of the new stack frame, so the program knows where to return once the function is finished.

