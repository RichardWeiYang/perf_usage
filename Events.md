Perf is an event-oriented observability tool, so first let's take a look
available events

# List events

## All events

```
perf list
```

to show all event current perf supports.

```
  branch-instructions OR branches                    [Hardware event]
  branch-misses                                      [Hardware event]
  bus-cycles                                         [Hardware event]
  cache-misses                                       [Hardware event]
  cache-references                                   [Hardware event]
  cpu-cycles OR cycles                               [Hardware event]
  instructions                                       [Hardware event]
  ref-cycles                                         [Hardware event]
  alignment-faults                                   [Software event]
  bpf-output                                         [Software event]
  context-switches OR cs                             [Software event]
  cpu-clock                                          [Software event]
  cpu-migrations OR migrations                       [Software event]
  dummy                                              [Software event]
  emulation-faults                                   [Software event]
  major-faults                                       [Software event]
  minor-faults                                       [Software event]
  page-faults OR faults                              [Software event]
  task-clock                                         [Software event]
  L1-dcache-load-misses                              [Hardware cache event]
  L1-dcache-loads                                    [Hardware cache event]
  L1-dcache-stores                                   [Hardware cache event]
  L1-icache-load-misses                              [Hardware cache event]
  LLC-load-misses                                    [Hardware cache event]
  LLC-loads                                          [Hardware cache event]
  LLC-store-misses                                   [Hardware cache event]
  LLC-stores                                         [Hardware cache event]
  branch-load-misses                                 [Hardware cache event]
  branch-loads                                       [Hardware cache event]
  dTLB-load-misses                                   [Hardware cache event]
  dTLB-loads                                         [Hardware cache event]
  dTLB-store-misses                                  [Hardware cache event]
  dTLB-stores                                        [Hardware cache event]
  iTLB-load-misses                                   [Hardware cache event]
  iTLB-loads                                         [Hardware cache event]
  node-load-misses                                   [Hardware cache event]
  node-loads                                         [Hardware cache event]
  node-store-misses                                  [Hardware cache event]
  node-stores                                        [Hardware cache event]
  branch-instructions OR cpu/branch-instructions/    [Kernel PMU event]
  branch-misses OR cpu/branch-misses/                [Kernel PMU event]
  bus-cycles OR cpu/bus-cycles/                      [Kernel PMU event]
  cache-misses OR cpu/cache-misses/                  [Kernel PMU event]
  cache-references OR cpu/cache-references/          [Kernel PMU event]
  cpu-cycles OR cpu/cpu-cycles/                      [Kernel PMU event]
  cstate_core/c3-residency/                          [Kernel PMU event]
  cstate_core/c6-residency/                          [Kernel PMU event]
  cstate_core/c7-residency/                          [Kernel PMU event]
  cstate_pkg/c2-residency/                           [Kernel PMU event]
  cstate_pkg/c3-residency/                           [Kernel PMU event]
  cstate_pkg/c6-residency/                           [Kernel PMU event]
  cstate_pkg/c7-residency/                           [Kernel PMU event]
  cycles-ct OR cpu/cycles-ct/                        [Kernel PMU event]
  cycles-t OR cpu/cycles-t/                          [Kernel PMU event]
  el-abort OR cpu/el-abort/                          [Kernel PMU event]
  el-capacity OR cpu/el-capacity/                    [Kernel PMU event]
  el-commit OR cpu/el-commit/                        [Kernel PMU event]
  el-conflict OR cpu/el-conflict/                    [Kernel PMU event]
  el-start OR cpu/el-start/                          [Kernel PMU event]
  i915/actual-frequency/                             [Kernel PMU event]
  i915/bcs0-busy/                                    [Kernel PMU event]
  i915/bcs0-sema/                                    [Kernel PMU event]
  i915/bcs0-wait/                                    [Kernel PMU event]
  i915/interrupts/                                   [Kernel PMU event]
  i915/rc6-residency/                                [Kernel PMU event]
  i915/rcs0-busy/                                    [Kernel PMU event]
  i915/rcs0-sema/                                    [Kernel PMU event]
  i915/rcs0-wait/                                    [Kernel PMU event]
  i915/requested-frequency/                          [Kernel PMU event]
  i915/vcs0-busy/                                    [Kernel PMU event]
  i915/vcs0-sema/                                    [Kernel PMU event]
  i915/vcs0-wait/                                    [Kernel PMU event]
  i915/vecs0-busy/                                   [Kernel PMU event]
  i915/vecs0-sema/                                   [Kernel PMU event]
  i915/vecs0-wait/                                   [Kernel PMU event]
  instructions OR cpu/instructions/                  [Kernel PMU event]
  mem-loads OR cpu/mem-loads/                        [Kernel PMU event]
  mem-stores OR cpu/mem-stores/                      [Kernel PMU event]
  msr/aperf/                                         [Kernel PMU event]
  msr/cpu_thermal_margin/                            [Kernel PMU event]
  msr/mperf/                                         [Kernel PMU event]
  msr/smi/                                           [Kernel PMU event]
  msr/tsc/                                           [Kernel PMU event]
  power/energy-cores/                                [Kernel PMU event]
  power/energy-gpu/                                  [Kernel PMU event]
  power/energy-pkg/                                  [Kernel PMU event]
  power/energy-ram/                                  [Kernel PMU event]
  ref-cycles OR cpu/ref-cycles/                      [Kernel PMU event]
  topdown-fetch-bubbles OR cpu/topdown-fetch-bubbles/ [Kernel PMU event]
  topdown-recovery-bubbles OR cpu/topdown-recovery-bubbles/ [Kernel PMU event]
  topdown-slots-issued OR cpu/topdown-slots-issued/  [Kernel PMU event]
  topdown-slots-retired OR cpu/topdown-slots-retired/ [Kernel PMU event]
  topdown-total-slots OR cpu/topdown-total-slots/    [Kernel PMU event]
  tx-abort OR cpu/tx-abort/                          [Kernel PMU event]
  tx-capacity OR cpu/tx-capacity/                    [Kernel PMU event]
  tx-commit OR cpu/tx-commit/                        [Kernel PMU event]
  tx-conflict OR cpu/tx-conflict/                    [Kernel PMU event]
  tx-start OR cpu/tx-start/                          [Kernel PMU event]
  uncore_cbox_0/clockticks/                          [Kernel PMU event]
  uncore_cbox_1/clockticks/                          [Kernel PMU event]
  uncore_cbox_2/clockticks/                          [Kernel PMU event]
  uncore_cbox_3/clockticks/                          [Kernel PMU event]
  uncore_imc/data_reads/                             [Kernel PMU event]
  uncore_imc/data_writes/                            [Kernel PMU event]

cache:
  l1d.replacement                                   
       [L1D data line replacements]
  l1d_pend_miss.fb_full                             
       [Cycles a demand request was blocked due to Fill Buffers inavailability]
  l1d_pend_miss.pending                             
       [L1D miss oustandings duration in cycles]
  l1d_pend_miss.pending_cycles                      
       [Cycles with L1D load Misses outstanding]
  l1d_pend_miss.pending_cycles_any                  
       [Cycles with L1D load Misses outstanding from any thread on physical
        core]
  l1d_pend_miss.request_fb_full                     
       [Number of times a request needed a FB entry but there was no entry
        available for it. That is the FB unavailability was dominant reason
        for blocking the request. A request includes cacheable/uncacheable
        demands that is load, store or SW prefetch. HWP are e]

... snip ...

Metric Groups:

DSB:
  DSB_Coverage
       [Fraction of Uops delivered by the DSB (aka Decoded Icache; or Uop Cache)]
Frontend:
  IFetch_Line_Utilization
       [Rough Estimation of fraction of fetched lines bytes that were likely consumed by program instructions]
Frontend_Bandwidth:
  DSB_Coverage
       [Fraction of Uops delivered by the DSB (aka Decoded Icache; or Uop Cache)]
Memory_BW:
  MLP
       [Memory-Level-Parallelism (average number of L1 miss demand load when there is at least 1 such miss)]
Memory_Bound:
  Load_Miss_Real_Latency
       [Actual Average Latency for L1 data-cache miss demand loads]
  MLP
       [Memory-Level-Parallelism (average number of L1 miss demand load when there is at least 1 such miss)]
Memory_Lat:
  Load_Miss_Real_Latency
       [Actual Average Latency for L1 data-cache miss demand loads]
Pipeline:
  CPI
       [Cycles Per Instruction (threaded)]
  ILP
       [Instruction-Level-Parallelism (average number of uops executed when there is at least 1 uop executed)]
  UPI
       [Uops Per Instruction]
Ports_Utilization:
  ILP
       [Instruction-Level-Parallelism (average number of uops executed when there is at least 1 uop executed)]
Power:
  C2_Pkg_Residency
       [C2 residency percent per package]
  C3_Core_Residency
       [C3 residency percent per core]
  C3_Pkg_Residency
       [C3 residency percent per package]
  C6_Core_Residency
       [C6 residency percent per core]
  C6_Pkg_Residency
       [C6 residency percent per package]
  C7_Core_Residency
       [C7 residency percent per core]
  C7_Pkg_Residency
       [C7 residency percent per package]
  Turbo_Utilization
       [Average Frequency Utilization relative nominal frequency]
SMT:
  CORE_CLKS
       [Core actual clocks when any thread is active on the physical core]
  CoreIPC
       [Instructions Per Cycle (per physical core)]
  SMT_2T_Utilization
       [Fraction of cycles where both hardware threads were active]
Summary:
  CLKS
       [Per-thread actual clocks when the logical processor is active. This is called 'Clockticks' in VTune]
  CPI
       [Cycles Per Instruction (threaded)]
  CPU_Utilization
       [Average CPU Utilization]
  Instructions
       [Total number of retired Instructions]
  Kernel_Utilization
       [Fraction of cycles spent in Kernel mode]
  SMT_2T_Utilization
       [Fraction of cycles where both hardware threads were active]
TLB:
  Page_Walks_Utilization
       [Utilization of the core's Page Walker(s) serving STLB misses triggered by instruction/Load/Store accesses]
TopDownL1:
  IPC
       [Instructions Per Cycle (per logical thread)]
  SLOTS
       [Total issue-pipeline slots]
Unknown_Branches:
  BAClear_Cost
       [Average Branch Address Clear Cost (fraction of cycles)]
```

## Show events in one category

There are too many events, it would be helpful to just show events in one
category.

Based on a non-accurate grep(perf list | grep ":\$"), currently it has
following groups:

  * cache
  * floating point
  * frontend
  * memory
  * other
  * pipeline
  * uncore
  * virtual memory

For example, list the events related to **cache**.

```
$perf list 'memory'

List of pre-defined events (to be used in -e):

  L1-dcache-load-misses                              [Hardware cache event]
  L1-dcache-loads                                    [Hardware cache event]
  L1-dcache-stores                                   [Hardware cache event]
  L1-icache-load-misses                              [Hardware cache event]
  LLC-load-misses                                    [Hardware cache event]
  LLC-loads                                          [Hardware cache event]
  LLC-store-misses                                   [Hardware cache event]
  LLC-stores                                         [Hardware cache event]
  branch-load-misses                                 [Hardware cache event]
  branch-loads                                       [Hardware cache event]
  dTLB-load-misses                                   [Hardware cache event]
  dTLB-loads                                         [Hardware cache event]
  dTLB-store-misses                                  [Hardware cache event]
  dTLB-stores                                        [Hardware cache event]
  iTLB-load-misses                                   [Hardware cache event]
  iTLB-loads                                         [Hardware cache event]
  node-load-misses                                   [Hardware cache event]
  node-loads                                         [Hardware cache event]
  node-store-misses                                  [Hardware cache event]
  node-stores                                        [Hardware cache event]
```

## Show Tracepoint event in category

Tracepoint event is a special category event, which is implemented by kernel ftrace.[?]

To list a summary of tracepoint events:

```
# perf list | awk -F: '/Tracepoint event/ { lib[$1]++ } END {
    for (l in lib) { printf "  %-16.16s: %d\n", l, lib[l] } }' | sort -t: -k2 -nr | column

     syscalls       : 626	   x86_fpu        : 12	   smbus          : 4	   ftrace         : 2
     ext4           : 105	   rtc            : 12	   rpm            : 4	   exceptions     : 2
     kvm            : 72	   kmem           : 12	   i2c            : 4	   cma            : 2
     xhci-hcd       : 48	   irq_matrix     : 12	   huge_memory    : 4	   vsyscall       : 1
     sunrpc         : 36	   filelock       : 11	   filemap        : 4	   udp            : 1
     irq_vectors    : 32	   cgroup         : 9	   bridge         : 4	   tlb            : 1
     writeback      : 29	   xdp            : 8	   alarmtimer     : 4	   sync_trace     : 1
     sched          : 24	   oom            : 8	   sock           : 3	   swiotlb        : 1
     power          : 23	   tcp            : 7	   skb            : 3	   rcu            : 1
     nfsd           : 23	   regulator      : 7	   msr            : 3	   qdisc          : 1
     block          : 18	   iommu          : 7	   initcall       : 3	   printk         : 1
     net            : 17	   dma_fence      : 7	   hwmon          : 3	   page_isolation : 1
     vmscan         : 16	   libata         : 6	   drm            : 3	   nmi            : 1
     jbd2           : 16	   thermal        : 5	   cpuhp          : 3	   napi           : 1
     clk            : 16	   scsi           : 5	   thermal_power_ : 2	   migrate        : 1
     regmap         : 15	   ras            : 5	   task           : 2	   mdio           : 1
     random         : 15	   percpu         : 5	   signal         : 2	   mce            : 1
     kvmmmu         : 14	   module         : 5	   rseq           : 2	   fib            : 1
     fs_dax         : 14	   irq            : 5	   raw_syscalls   : 2
     compaction     : 14	   workqueue      : 4	   pagemap        : 2
     timer          : 13	   wbt            : 4	   gpio           : 2
```

From the above output, we can see syscalls has the most number of trace points.

Then if you want to see the tracepoint in one category, use the following command.

```
# perf list 'sched:*'

sched:sched_kthread_stop                           [Tracepoint event]
sched:sched_kthread_stop_ret                       [Tracepoint event]
sched:sched_migrate_task                           [Tracepoint event]
sched:sched_move_numa                              [Tracepoint event]
sched:sched_pi_setprio                             [Tracepoint event]
sched:sched_process_exec                           [Tracepoint event]
sched:sched_process_exit                           [Tracepoint event]
sched:sched_process_fork                           [Tracepoint event]
sched:sched_process_free                           [Tracepoint event]
sched:sched_process_hang                           [Tracepoint event]
sched:sched_process_wait                           [Tracepoint event]
sched:sched_stat_blocked                           [Tracepoint event]
sched:sched_stat_iowait                            [Tracepoint event]
sched:sched_stat_runtime                           [Tracepoint event]
sched:sched_stat_sleep                             [Tracepoint event]
sched:sched_stat_wait                              [Tracepoint event]
sched:sched_stick_numa                             [Tracepoint event]
sched:sched_swap_numa                              [Tracepoint event]
sched:sched_switch                                 [Tracepoint event]
sched:sched_wait_task                              [Tracepoint event]
sched:sched_wake_idle_without_ipi                  [Tracepoint event]
sched:sched_wakeup                                 [Tracepoint event]
sched:sched_wakeup_new                             [Tracepoint event]
sched:sched_waking                                 [Tracepoint event]
```

# Event selection

Since perf is event oriented, one of the process to use it is to specify the event we want to monitor.

Generally, "-e" option is used to specify the event, while we may have several important cases.

## Specify particular event

```
perf stat -e cycles dd if=/dev/zero of=/dev/null count=100000
```

cycles is one event in perf stat, use "-e cycles" to specify to monitor this event.

And perf supports to specify several events

```
perf stat -e cycles,instructions dd if=/dev/zero of=/dev/null count=100000
```

### Modifiers

Events can optionally have a modifier by appending a colon and one or more modifiers.

Modifiers  | Description | Example
  ------------- | -------------
  u	| monitor at priv level 3, 2, 1 (user)	| event:u
  k	| monitor at priv level 0 (kernel)	    | event:k
  h	| monitor hypervisor events on a virtualization environment	| event:h
  H	| monitor host machine on a virtualization environment	| event:H
  G	| monitor guest machine on a virtualization environment	| event:G

So the above command could be changed to

```
perf stat -e cycles:u dd if=/dev/zero of=/dev/null count=100000
```

Then this will only count user level events.
