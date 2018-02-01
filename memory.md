# Memory In Linux

## What is RSS?
**RSS** stands for Resident Set Size and is used to show how much
memory is allocated to that process and is in RAM. It includes all
stack and heap memory.

## What is VSZ?
**VSZ** stands for Virtual Memory Size. It includes all the memory
that the process can acccess including memoery that is swapped out
and memory that is from shared libraries.

## Memory Leaks Vs. Memory Bloats

## How to tell if you have a memory leak in your rails app?

To tell if you have a memory leak in your rails app you should hit
an endpoint repeatedly. If the memory usage continously goes up endlessly
at that endpoint, then you have memory leaking. If the memory levels out
then you have memory bloat.
