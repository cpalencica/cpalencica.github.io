---
layout: default
title: CPU Design & Architecture Projects
description: Projects exploring computer architecture, CPU design, and cache optimization.
---

# CPU Design & Architecture Projects

Explore my work in computer architecture through digital CPU design, simulation environments, and memory hierarchy optimizations. These projects demonstrate an understanding of low-level systems, RTL design, and performance-enhancing strategies for modern computing systems.

---

**Jump to Project:**  
[Custom CPU Design](#custom-cpu-design---verilog-implementation)  
[Cache Replacement Policy](#cache-replacement-policy---lfuda-in-gem5)

---

## Custom CPU Design – Verilog Implementation

**Description:**  
Designed and implemented a custom 5-stage pipelined CPU in Verilog to execute a subset of the RISC-V instruction set. The project focused on instruction/data memory interfacing, control logic, forwarding, and hazard detection units, verified using ModelSim and synthesized with Quartus.

**Technologies Used:** Verilog, RISC-V, ModelSim, Quartus, 5-Stage Pipeline

**Key Features:**
- Implements a 5-stage RISC-V pipeline: IF, ID, EX, MEM, WB  
- Data hazard handling via forwarding and hazard detection units  
- Branch prediction with PC muxing logic and control flow resolution in the ID stage  
- Synchronous instruction and data memory modules  
- Testbench-driven validation using ModelSim  
- Final implementation runs RISC-V assembly programs with correct cycle timing

**Modules Implemented:**
- ALU, Register File, Control Unit  
- Hazard Detection & Forwarding Units  
- Pipeline Registers and Clock Gating  
- Instruction/Data Memory with simulation waveform debugging

**GitHub:** [View Repository](https://github.com/cpalencica/cpuDesign)

---

## Cache Replacement Policy – LFUDA in gem5

**Description:**  
Implemented the Least Frequently Used with Dynamic Aging (LFUDA) cache replacement algorithm in the gem5 simulator. LFUDA balances access frequency with recency by dynamically aging counters, avoiding cache pollution from frequent but outdated data.

**Technologies Used:** C++, gem5, Computer Architecture, Cache Replacement Algorithms

**Key Features:**
- Modified gem5’s cache replacement interface to support LFUDA  
- Maintains aging-adjusted frequency counters to prioritize evictions  
- Integrated into gem5’s LRU replacement framework using custom policy hooks  
- Evaluated against LRU and LFU using SPEC-like traces  
- Demonstrated improvement in hit rate and reduced cache pollution in select workloads

**Implementation Details:**
- Frequency counters incremented on access  
- Global aging value updated on each eviction  
- Effective frequency = access count + global aging  
- Eviction policy selects block with lowest effective frequency

**GitHub:** [View Repository](https://github.com/cpalencica/LFUDA)

---
