This time we want to analysis who triggers external irq the most. While current infrastructure doesn't support this, we need to add an event to track this.

# Add an new event kvm_extirq

The [patch][1] file lists the changes necessary.

# Analysis

Then the analysis is simple, execute following command:

```
perf record -e 'kvm:kvm_extirq2' -a sleep 30
perf report
```

The result looks like this:

```
# 78.01%  Ext irq2 0 - vec 253 causing vmexit
# 18.05%  Ext irq2 0 - vec 236 causing vmexit
#  2.22%  Ext irq2 124 - vec 33 causing vmexit
#  0.83%  Ext irq2 0 - vec 252 causing vmexit
#  0.69%  Ext irq2 0 - vec 251 causing vmexit
#  0.15%  Ext irq2 125 - vec 33 causing vmexit
#  0.05%  Ext irq2 123 - vec 33 causing vmexit
```

[1]: https://gist.github.com/RichardWeiYang/b6bbe7b1291d2ff815bc322f0ec10505
