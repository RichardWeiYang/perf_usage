perf stat is the command with lowest overhead, since it just **counting** events in-kernel context.

# Basic usage

The basic usage for perf stat is "perf stat command". This will counting events for the command.

```
perf stat -B dd if=/dev/zero of=/dev/null count=1000000

1000000+0 records in
1000000+0 records out
512000000 bytes (512 MB) copied, 0.956217 s, 535 MB/s

 Performance counter stats for 'dd if=/dev/zero of=/dev/null count=1000000':

            5,099 cache-misses             #      0.005 M/sec (scaled from 66.58%)
          235,384 cache-references         #      0.246 M/sec (scaled from 66.56%)
        9,281,660 branch-misses            #      3.858 %     (scaled from 33.50%)
      240,609,766 branches                 #    251.559 M/sec (scaled from 33.66%)
    1,403,561,257 instructions             #      0.679 IPC   (scaled from 50.23%)
    2,066,201,729 cycles                   #   2160.227 M/sec (scaled from 66.67%)
              217 page-faults              #      0.000 M/sec
                3 CPU-migrations           #      0.000 M/sec
               83 context-switches         #      0.000 M/sec
       956.474238 task-clock-msecs         #      0.999 CPUs

       0.957617512  seconds time elapsed
```

# Repeated measurement

perf could run test multiple times and get the standard deviation from the mean.

```
perf stat -r 5 sleep 1

 Performance counter stats for 'sleep 1' (5 runs):

    <not counted> cache-misses
           20,676 cache-references         #     13.046 M/sec   ( +-   0.658% )
            6,229 branch-misses            #      0.000 %       ( +-  40.825% )
    <not counted> branches
    <not counted> instructions
    <not counted> cycles
              144 page-faults              #      0.091 M/sec   ( +-   0.139% )
                0 CPU-migrations           #      0.000 M/sec   ( +-    -nan% )
                1 context-switches         #      0.001 M/sec   ( +-   0.000% )
         1.584872 task-clock-msecs         #      0.002 CPUs    ( +-  12.480% )

       1.002251432  seconds time elapsed   ( +-   0.025% )
```

# Specify target

By default, perf counts all threads of the process, while you could specify the target with options.

  Option  | Example | Description
  ------------- | -------------
  -i | | child task do not inherit counters
  -p | -p pid | stat on existing process id
  -t | -t tid | stat on existing thread id
  -a | | system-wide collection from all CPUs
  -C | -C 0-3,5 | count only on list of CPUs

# Controlling output

perf also has options to control the output.

Option  | Example | Description
------------- | -------------
-B | | Big Number
-x | -x, | programmable friendly output
--table | | Display time for each run (-r) in a table format

```
perf stat  -x, date
```
