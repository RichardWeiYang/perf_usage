The perf tool can be used to collect profiles on per-thread, per-process and per-cpu basis.

There are several commands associated with sampling:

* record
* report
* annotate

You must first collect the samples using perf record. This generates an output file called perf.data. That file can then be analyzed, possibly on another machine, using the perf report and perf annotate commands.

# Collecting Samples

Different from perf stat, perf record is a sampling system. And there are two modes of sampling period:

Mode  | Example | Description
------------- | -------------
-c | -c 2000 | to collect a sample every 2000 occurrences of event
-F | -F 250  | sampling at 250HZ

By default, -F 1000 is used.

Also another useful option is **"-g"**, this will aggregate child functions which may help to give you a better understanding.

# Analysis with perf report

perf report will read perf.data by default and generates a concise execution profile.

```
Samples: 7  of event 'cycles:ppp', Event count (approx.): 3499872
Overhead  Command  Shared Object     Symbol
  91.67%  sleep    [kernel.vmlinux]  [k] sync_regs
   8.04%  sleep    [kernel.vmlinux]  [k] vma_adjust_trans_huge
   0.28%  perf     [kernel.vmlinux]  [k] end_repeat_nmi
   0.01%  perf     [kernel.vmlinux]  [k] wrmsrl
```

The meaning of those fields.

* Overhead: percentage of this function
* Command:  process from which the samples were collected
* Shared O: the ELF name
* Privilege: the privilege level at which the sample was taken
* Symbol:   symbol name

For the field Privilege, there are several conditions:

 Character | Meaning
 ------------- | -------------
 [.] | user level
 [k] | kernel level
 [g] | guest kernel level
 [u] | guest user level
 [H] | Hypervisor

# Control Output

For perf report, there are several options to control output.

## sort

By default, the output is sorted by Overhead. If you want to change it, use --sort option.

There is a long list of sort keys in manual, just list few here.

Key | Example | Meaning
------------- | -------------
comm   | | command name of the task
pid    | | command and tid of task
dso    | | name of library or module executed
symbol | | name of function executed
cpu    | | cpu number the task ran at
