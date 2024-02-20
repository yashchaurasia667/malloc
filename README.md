We will implement malloc(), calloc(), realloc() and free()

The memory allocator will not be fast or efficient, we will not adjust allocated memory to align with the size of the page boundary, but we will build a memory allocator that works!

Before we get into building the memory allocator, you need to be familiar with the memory layout of a program. A process runs within its own virtual address space that’s distinct from the virtual address spaces of other processes. This virtual address space typically comprises of 5 sections:

Text section: The part that contains the binary instructions to be executed by the processor.
Data section: Contains non-zero initialized static data.
BSS (Block Started by Symbol) : Contains zero-initialized static data. Static data uninitialized in program is initialized 0 and goes here.
Heap: Contains the dynamically allocated data.
Stack: Contains your automatic variables, function arguments, copy of base pointer etc.

<h2>malloc()</h2>

The malloc(size) function allocates size bytes of memory and returns a pointer to the allocated memory.