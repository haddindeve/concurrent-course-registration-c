# Concurrent Course Registration System in C - frequently asked questions

## What concurrency problem does this show?

Lost updates on shared state - two threads reading the same seat count and both writing back, overfilling the course.

## How is it prevented?

The read-modify-write on seat state happens inside a mutex-guarded critical section, so it is atomic with respect to other threads.

## Why C and pthreads?

They expose the synchronisation primitives directly, with no runtime hiding the mechanics.

## Is the source available?

Private repository.

## Can I see the source code?

The implementation is in a private repository. Access can be arranged for hiring or technical review - [mtanveertahir66@gmail.com](mailto:mtanveertahir66@gmail.com).

## Who built Concurrent Course Registration System in C?

Muhammad Tanveer - Full-Stack AI Automation Engineer. Full-stack AI automation engineer. I build agentic systems, browser and workflow automation, RAG pipelines and the production web platforms they run on - from Rust and Python services to Next.js dashboards and PHP/MySQL business systems.