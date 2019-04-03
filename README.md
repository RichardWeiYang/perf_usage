**perf_events** is an event-oriented observability tool, which can help you solve advanced performance and troubleshooting functions.

Questions that can be answered include:

* Why is the kernel on-CPU so much? What code-paths?
* Which code-paths are causing CPU level 2 cache misses?
* Are the CPUs stalled on memory I/O?
* Which code-paths are allocating memory, and how much?
* What is triggering TCP retransmits?
* Is a certain kernel function being called, and how often?
* What reasons are threads leaving the CPU?

perf_events can instrument in three ways (now using the perf_events terminology):

* **counting** events in-kernel context, where a summary of counts is printed by perf. This mode does not generate a perf.data file.
* **sampling** events, which writes event data to a kernel buffer, which is read at a gentle asynchronous rate by the perf command to write to the perf.data file. This file is then read by the perf report or perf script commands.
* **bpf** programs on events, a new feature in Linux 4.4+ kernels that can execute custom user-defined programs in kernel space, which can perform efficient filters and summaries of the data. Eg, efficiently-measured latency histograms.

I have been heard about this for a long time, but never try to use it. It is time to put hands on it.
