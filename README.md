# Concurrent Course Registration System in C

> Multi-threaded course registration simulation in C, using POSIX threads to handle contested seats safely.

Built by **[Muhammad Tanveer](https://www.linkedin.com/in/muhammad-tanveer-advenno/)** - Full-Stack AI Automation Engineer.

[![Source](https://img.shields.io/badge/source-private%20repository-lightgrey)](#source-code-and-access) [![Role](https://img.shields.io/badge/built%20by-Muhammad%20Tanveer-blue)](https://github.com/haddindeve)

## Contents

- [The problem](#the-problem)
- [The approach](#the-approach)
- [Architecture](#architecture)
- [Tech stack](#tech-stack)
- [Key capabilities](#key-capabilities)
- [Selected code](#selected-code)
- [Results](#results)
- [FAQ](#faq)
- [Source code and access](#source-code-and-access)
- [About the engineer](#about-the-engineer)
- [Related projects](#related-projects)

## The problem

Course registration is a textbook concurrency problem: many students contend for a limited number of seats at once. Without correct synchronisation a course is overfilled, and the bug only appears under load.

## The approach

A POSIX threads simulation where each student is a thread contending for shared seat state. Access is guarded so the seat count cannot be read and written unsafely, making overfilling impossible rather than merely unlikely.

## Architecture

| Component | Responsibility |
| --- | --- |
| **Thread model** | One thread per registering student |
| **Shared state** | Course seat counts under explicit synchronisation |
| **Synchronisation** | Mutex-guarded critical sections |
| **Simulation driver** | Concurrent load generation and reporting |

## Tech stack

| Layer | Technology |
| --- | --- |
| Language | C |
| Concurrency | POSIX threads (pthreads) |
| Synchronisation | Mutexes over shared seat state |
| Build | Makefile |

## Key capabilities

- Thread-per-student concurrency model
- Mutex-protected seat allocation
- Race condition prevention under contention
- Reproducible concurrent simulation

## Selected code

From `src/main.c` in the private repository:

```c
#include <pthread.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <time.h>

typedef enum {
    PRIORITY_LOW = 0,
    PRIORITY_NORMAL = 1,
    PRIORITY_HIGH = 2
} Priority;

typedef struct {
    int student_id;
    Priority priority;
    char course_id[16];
} StudentRequest;
```

## Results

- Seat limits hold under concurrent contention
- Demonstrates the failure mode and the synchronisation that removes it

## FAQ

### What concurrency problem does this show?

Lost updates on shared state - two threads reading the same seat count and both writing back, overfilling the course.

### How is it prevented?

The read-modify-write on seat state happens inside a mutex-guarded critical section, so it is atomic with respect to other threads.

### Why C and pthreads?

They expose the synchronisation primitives directly, with no runtime hiding the mechanics.

### Is the source available?

Private repository.

## Source code and access

This repository is the public case study for **Concurrent Course Registration System in C**. The full implementation - application code, database schema, tests and deployment configuration - lives in a **private repository** on this account, alongside the rest of the work shown here.

Source access can be arranged for hiring conversations, technical review or client due diligence. The quickest route is a short message on [LinkedIn](https://www.linkedin.com/in/muhammad-tanveer-advenno/) or an email to [mtanveertahir6666@gmail.com](mailto:mtanveertahir6666@gmail.com).

## About the engineer

**Muhammad Tanveer - Full-Stack AI Automation Engineer**

Full-stack AI automation engineer. I build agentic systems, browser and workflow automation, RAG pipelines and the production web platforms they run on - from Rust and Python services to Next.js dashboards and PHP/MySQL business systems.

- GitHub: [haddindeve](https://github.com/haddindeve)
- LinkedIn: [Muhammad Tanveer](https://www.linkedin.com/in/muhammad-tanveer-advenno/)
- Email: [mtanveertahir6666@gmail.com](mailto:mtanveertahir6666@gmail.com)
- Location: Pakistan

## Related projects

- [ATM Electronic Journal Parser and GL Reconciliation](https://github.com/haddindeve/ej-rolls-atm-reconciliation)
- [AuthentID - eMRTD Chip Identity Verification](https://github.com/haddindeve/authentid-emrtd-face-verification)
- [Doctern - AI Document OCR and Table Extraction](https://github.com/haddindeve/doctern-document-ocr-ai)
- [Lunaria - Privacy-First Women's Wellness App](https://github.com/haddindeve/lunaria-womens-wellness-app)
- [Advenno - Agency Platform with Client and Employee Portals](https://github.com/haddindeve/advenno-agency-saas-platform)
- [LinkedIn Lead Finder and Analyser](https://github.com/haddindeve/linkedin-lead-finder-and-analyser)

---

<sub>Concurrent Course Registration System in C - case study by Muhammad Tanveer - Full-Stack AI Automation Engineer. Keywords: POSIX threads C, concurrent programming, thread synchronisation, race condition prevention, mutex semaphore, operating systems project.</sub>