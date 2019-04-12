During some test with "perf stat", we found event "kvm_pio" is heavy. So we decide to see who is the criminal.

# Record Events

First step is use perf record to record events.

```
perf record -e 'kvm:kvm_pio' -a sleep 30
```

This will general perf.data file.

# Dump raw data

After this, we need to take a look into the raw data.

```
perf script > pio_stat
```

Now pio_stat contains the raw data. Here is a glance of the raw data.

```
qemu-system-x86 10042 [000] 313831.754508: kvm:kvm_pio: pio_read at 0x3fd size 1 count 1 val 0x60
qemu-system-x86 10042 [000] 313831.754515: kvm:kvm_pio: pio_read at 0x3fd size 1 count 1 val 0x60
```

# Use awk to analysis

Execute this:

```
awk -f pio_calculate.awk pio_stat | sort -nk 2 -r
```

The pio_calculate.awk looks like:

```
{
	if ($0 ~ /pio_write/) {
		ops["W:"$8]++
	} else if ($0 ~ /pio_read/) {
		ops["R:"$8]++
	}
}

END {
	for (op in ops) {
		printf "%-16.16s %d\n", op, ops[op]
	}
}
```

Then you will get this output:

```
R:0x3fd          9994
R:0x3fb          4
W:0x20           1
```

This shows most pio operation happens at port 0x3fd.

# Find the criminal

Then we can use file /proc/ioport to find the port 0x3fd belongs to who.

Go and find it!
