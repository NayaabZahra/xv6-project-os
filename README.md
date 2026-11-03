# XV6 RISC-V Kernel Extension: Operating Systems Project

## Project Overview
This project extends the MIT `xv6-riscv` educational operating system by introducing five advanced Operating Systems modules. The goal is to enhance process visibility, scheduling fairness, memory tracking, inter-process communication, and file security.

- **Base Kernel:** MIT xv6-riscv
- **Development Environment:** Windows (Host) / QEMU Emulator with RISC-V Toolchain
- **Group Size:** 3 Members

---

## Implemented / Proposed Modules

### Module 1: Advanced Process Management and Monitoring
* **Objective:** Provide detailed telemetry and live monitoring of running processes.
* **Components:** 
  1. Process Information Collector
  2. Process State Monitor
  3. CPU Usage Tracker
  4. Process Statistics Table
  5. Process Monitoring System Call
* **Working Mechanism:** Reads data directly from the kernel process table (`ptable`) via a new system call, exposing live execution states and resource consumption to user-space utilities.

### Module 2: Priority-Based CPU Scheduling with Aging
* **Objective:** Replace/augment round-robin scheduling with priority-driven execution and starvation prevention.
* **Components:** 
  1. Priority Assignment Manager
  2. Priority-Based Scheduler
  3. Aging Mechanism
  4. Waiting-Time Tracker
  5. Scheduling Statistics Collector
* **Working Mechanism:** Assigns priority levels to processes. The scheduler selects the highest-priority runnable process, while an aging mechanism gradually increases the priority of long-waiting tasks to prevent starvation.

### Module 3: Smart Memory Allocation and Monitoring
* **Objective:** Track kernel memory allocations, deallocations, and physical page utilization.
* **Components:** 
  1. Memory Allocation Tracker
  2. Memory Deallocation Monitor
  3. Physical Page Usage Counter
  4. Memory Statistics Collector
  5. Memory Reporting Interface
* **Working Mechanism:** Hooks into `kalloc` and `kfree` to monitor free/allocated page counts and report memory health statistics to user programs.

### Module 4: Kernel-Level Message Queue Communication
* **Objective:** Enable structured inter-process communication through kernel-managed message queues.
* **Components:** 
  1. Message Queue Manager
  2. Message Storage Buffer
  3. Send Message System Call
  4. Receive Message System Call
  5. Queue Synchronization Mechanism
* **Working Mechanism:** Implements `msgsnd` and `msgrcv` system calls backed by kernel buffers, protected with process sleep/wakeup synchronization primitives.

### Module 5: Enhanced File Access Control and Storage Quotas
* **Objective:** Enforce user-level file permissions and disk storage consumption limits.
* **Components:** 
  1. File Ownership Manager
  2. Permission Management Component
  3. Access Validation Module
  4. Storage Usage Tracker
  5. Quota Enforcement Mechanism
* **Working Mechanism:** Associates user IDs with file inodes. Validates read/write operations against user permissions and tracks storage usage to reject writes exceeding user quotas.

---

## Group Contributions
* **Member 1:** Process Management & Priority Scheduling (Modules 1 & 2)
* **Member 2:** Memory Allocation, Message Queues & File Quotas (Modules 3, 4 & 5)
* **Member 3:** Integration support, testing, and documentation verification.

