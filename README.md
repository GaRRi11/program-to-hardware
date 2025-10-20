## C Program Flow to Assembly

<img width="1049" height="734" alt="c drawio (2)" src="https://github.com/user-attachments/assets/98209edc-5681-4772-9702-b97ae7e9bbb9" />

1. Source Code (file.c)
Human-readable code written by the programmer. Example:
2. Preprocessor
| Step | Directive         | Action                                           |
| ---- | ----------------- | ------------------------------------------------ |
| 1    | `#include`        | Inserts all contents of header file (`stdio.h`). |
| 2    | `#define`         | Replaces macros (e.g., `PI → 3.14`).             |
| 3    | `#ifdef / #endif` | Includes/excludes code based on conditions.      |
| 4    | Comments          | Removed.                                         |
3.Compiler

<pre> ``` .section .data
g:
    .long 5
 ``` </pre>

.data: initialized data section

g: global variable with value 5 (32-bit integer → 4 bytes)
