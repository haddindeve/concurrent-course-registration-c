# Concurrent Course Registration System in C - architecture

A POSIX threads simulation where each student is a thread contending for shared seat state. Access is guarded so the seat count cannot be read and written unsafely, making overfilling impossible rather than merely unlikely.

## Components

### Thread model

One thread per registering student

### Shared state

Course seat counts under explicit synchronisation

### Synchronisation

Mutex-guarded critical sections

### Simulation driver

Concurrent load generation and reporting

## Stack

| Layer | Technology |
| --- | --- |
| Language | C |
| Concurrency | POSIX threads (pthreads) |
| Synchronisation | Mutexes over shared seat state |
| Build | Makefile |

Designed and implemented by Muhammad Tanveer - Full-Stack AI Automation Engineer.