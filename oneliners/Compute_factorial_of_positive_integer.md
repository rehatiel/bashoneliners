# Compute factorial of positive integer

## Command:
```
$ fac() { (echo 1; seq $1) | paste -s -d\* | bc; }
```

## Explanation:
Explanation
This one-liner defines a shell function named fac that computes the factorial of a positive integer. Once this function has been defined (you can put it in your .bashrc), you can use it as follows:
$ fac 10
3628800

Let's break the function down. Assume that we want to compute the factorial of 4. First, it echo's 1, so that the factorial of 0 works correctly (because seq 0 outputs nothing). Then, seq is used to generate a list of numbers: 
$ (echo 1; seq 4)
1
1
2
3
4

Then, it uses paste to put these numbers on one line, with * (multiplication) as the seperator:
$ (echo 1; seq 4) | paste -s -d\*
1*1*2*3*4

Finally, it passes this "equation" to bc, which evalutes it:
$ (echo 1; seq 4) | paste -s -d\* | bc
24

The actual function uses $1 so that we can compute the factorial of any positive integer using fac.

## Limitations:
Limitations
If a positive integer is not the one and only argument passed to it when invoked by the user, the result will be nonsense or an error will be thrown.

