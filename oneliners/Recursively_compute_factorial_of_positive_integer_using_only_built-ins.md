# Recursively compute factorial of positive integer using only built-ins

## Command:
```
$ bang() ( IFS=\*; let N=$1-1 k="$*" && bang $N $k || echo ${2-1} )
```

## Explanation:
Explanation
A recursive function that leverages the arithmetic expansions evaluated by the let command, and the significance of the field separator when arguments are expanded using "$*".


IFS=\* concatenates the arguments "$*" using a * symbol, which let interprets as a multiplication operator;


let N=$1-1 k="$*" assigns arithmetic values to variables N and k.  N will have a value one less than the first argument; k will be the product of all the arguments;


&& performs the command immediately to its right iff the expression immediately to its left evaluates to true;


bang $N $k calls itself with the first argument being one less than it was, and the second argument being the cumulative product of the arguments thus far across all iterations;


|| performs the command immediately to its right iff the command immediately to its left wasn't performed;


echo ${2-1} prints the second argument, which—if there is one—will be the factorial, otherwise it prints 1.

## Limitations:
Limitations
If a positive integer is not the one and only argument passed to it when invoked by the user, the result will be nonsense or an error will be thrown.

