# Concurrent Course Registration System in C - case study

**Engineer:** Muhammad Tanveer - Full-Stack AI Automation Engineer  
**Repository:** https://github.com/haddindeve/concurrent-course-registration-c

## Context

Course registration is a textbook concurrency problem: many students contend for a limited number of seats at once. Without correct synchronisation a course is overfilled, and the bug only appears under load.

## What I built

A POSIX threads simulation where each student is a thread contending for shared seat state. Access is guarded so the seat count cannot be read and written unsafely, making overfilling impossible rather than merely unlikely.

## Capabilities delivered

- Thread-per-student concurrency model
- Mutex-protected seat allocation
- Race condition prevention under contention
- Reproducible concurrent simulation

## Outcome

- Seat limits hold under concurrent contention
- Demonstrates the failure mode and the synchronisation that removes it

## Source

The implementation is held in a private repository. Access can be arranged on request - [mtanveertahir66@gmail.com](mailto:mtanveertahir66@gmail.com) or [LinkedIn](https://www.linkedin.com/in/muhammad-tanveer-advenno/).