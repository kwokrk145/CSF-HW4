CONTRIBUTIONS

TODO: write a brief summary of how each team member contributed to
the project.

Madhumitha Rajaprakash: Completed Tasks 1 + 2
Ryan Kwok: Completed Tasks 3 + 4

REPORT

TODO: add your report according to the instructions in the
"Experiments and analysis" section of the assignment description.

RESULTS:

Test run with threshold 2097152

real    0m0.716s
user    0m0.672s
sys     0m0.034s
Test run with threshold 1048576

real    0m0.393s
user    0m0.666s
sys     0m0.052s
Test run with threshold 524288

real    0m0.266s
user    0m0.667s
sys     0m0.068s
Test run with threshold 262144

real    0m0.213s
user    0m0.686s
sys     0m0.100s
Test run with threshold 131072

real    0m0.196s
user    0m0.663s
sys     0m0.133s
Test run with threshold 65536

real    0m0.179s
user    0m0.671s
sys     0m0.197s
Test run with threshold 32768

real    0m0.175s
user    0m0.729s
sys     0m0.258s
Test run with threshold 16384

real    0m0.187s
user    0m0.876s
sys     0m0.462s

Data Organized in Table:

Threshold       Real        
2097152         0.716s
1048576         0.393s
524288          0.266s
262144          0.213s
131072          0.196s
65536           0.179s
32768           0.175s
16384           0.187s

We can see for the first threshold, since the threshold is so high, the execution or operation is
mostly sequential. That's why as the threshold decreases, we can see that the recursive
forks more child processes, leading to a decrease in the Real time. However, we can see that
when the threshold becomes too small, (i.e. 16384), repeatedly calling fork() and waitpid() becomes
too costly and it overall outweighs the benefit of parallelism. More specifically, at smaller thresholds, 
the number of child processes becomes too large and it becomes hard to manage them. In addition, 
we can see that the user time remains pretty constant since the same number of comparisons and swaps need to
be performed, but the system time increases with more and more forks since time is spent managing them.  