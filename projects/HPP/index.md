---
layout: default
title: High Performance Programming Projects
description: Projects focused on optimizing numerical algorithms using parallelism and memory hierarchy techniques on multicore CPUs and GPUs.
---

# High Performance Programming Projects

These projects explore algorithmic and architectural optimizations for computationally intensive problems. They demonstrate my ability to accelerate performance through multithreading, memory blocking, OpenMP, CUDA, and cache-aware strategies.

---

**Jump to Project:**  
[Optimized Matrix Multiplication](#optimized-matrix-multiplication---cpu--gpu-parallelism) •  
[Optimized Successive Over-Relaxation](#optimized-successive-over-relaxation---sor)

---

## Optimized Matrix Multiplication – CPU & GPU Parallelism

**Description:**  
This project explores a wide range of performance optimizations for dense matrix-matrix multiplication (MMM) on both CPUs and GPUs. Techniques include loop transformations, loop blocking, OpenMP threading, CUDA kernel acceleration, and distributed computing using MPI and the SUMMA algorithm. Each implementation was benchmarked for performance and evaluated for parallel scalability and memory efficiency.

**Technologies Used:** C, OpenMP, CUDA, MPI

---

### Optimization Approaches

- **Blocked CPU MMM:**  
  - Cache-aware loop tiling improves temporal and spatial locality  
  - Configurable loop orders for analyzing access patterns  

- **OpenMP MMM:**  
  - Parallelization of outer loops across CPU threads  
  - Improved speedup on multicore systems  

- **CUDA MMM (Global + Shared Memory):**  
  - Global kernel uses direct global memory access  
  - Shared memory kernel employs tiling for memory coalescing and reduced latency  

- **Dense MMM with MPI + OpenMP (SUMMA):**  
  - Distributed matrix multiplication using 2D process grids  
  - Local submatrix multiplication parallelized with OpenMP  
  - Overlapped communication and computation for scalability 

---

**GitHub:** [View Repository](https://github.com/cpalencica/MMMoptimizations)  

---

## Optimized Successive Over-Relaxation – SOR

**Description:**  
Parallelized the Successive Over-Relaxation method for solving Laplace-like problems using pthreads, OpenMP, and CUDA. Each version was tuned for performance using proper domain decomposition, synchronization, and memory access optimization strategies.

**Technologies Used:** C, POSIX Threads (pthreads), OpenMP, CUDA

**Optimizations Explored:**
- **Pthreads Version:** Manual thread management with barriers and careful partitioning  
- **OpenMP Version:** Loop parallelization and scheduling strategies for shared-memory systems  
- **CUDA Version:** GPU acceleration with global memory access and coalesced reads  

**Evaluation Metrics:**
- Total runtime vs. baseline serial version  
- GPU memory access efficiency
- Thread scaling behavior on multicore CPU

**GitHub:** [View Repository](https://github.com/cpalencica/SORoptimizations)  

---
