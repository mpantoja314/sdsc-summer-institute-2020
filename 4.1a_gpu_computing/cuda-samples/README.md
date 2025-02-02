# CUDA samples

SDSC Summer Institute

August 6, 2020

Material by Andreas Goetz (agoetz@sdsc.edu).
Partly based on work by Mark Harris - NVIDIA corporation.

Directory content as explained below. 

For exercises see subdirectories `exercise/`, which contain CUDA
code that needs either fixing or improving. See comment in the
source code.

---
## Hello world

`hello_world_cpu.c`
Standard C "Hello World" program.
Can be compiled with standard C compiler or NVIDIA nvcc CUDA compiler.

`hello_world_cpu2.cu`
Identical to the standard C "Hello World" program.
Can be compiled with nvcc.

`hello_world_device.cu`
Contains a GPU kernel that will be executed on the GPU.
The kernel does not compute anything. However, printing from a kernel
is possible, so each of the threads says "Hello World".

---
## Addition

`add_gpu.cu`
CUDA program that adds two integer numbers on the GPU.

`vector_add_cpu.c`
C program for simple vector addition on the CPU.

`vector_add_gpu.cu`
CUDA program for simple vector addition on the GPU.
Launches all kernels at once.

`vector_add_gpu2.cu`
Same as above but launches fixed number of kernels.

---
## Squaring numbers in an array

`square_array.cu`
CUDA program to square matrix elements of an arbitrary size matrix 
in parallel on the GPU. Uses two-dimensional grids/blocks.

---
## 1D stencil

`1d_stencil.cu`
CUDA program that performs 1D stencil operation in parallel on the GPU
for an arbitrary sized vector. Boundary halos are set to zero. This could be
changed for example to periodic boundary conditions.
Uses shared memory to optimize performance as well as thread synchronization
within blocks.
