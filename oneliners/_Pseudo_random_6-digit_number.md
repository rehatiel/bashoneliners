# (Pseudo)random 6-digit number

## Command:
```
$ let N=0 N=N+10**{0..5}*${RANDOM:0:1}
```

## Explanation:
Explanation
Rather than calling out to python to create a pseudorandom number, we can use the builtin functions of bash to do this more quickly and with less code.
$RANDOM is the builtin random number function in bash.  It yields an integer up to 5 digits in length, so this method elects to sample just the first digit from each of the six calls made to $RANDOM.  let lends its arithmetic capabilities to construct the 6-digit result piecewise, so that:
𝑵 = 𝒙₁ + 10𝒙₂ + 100𝒙₃ + 1000𝒙₄ + 10000𝒙₅ + 100000𝒙₆
where 𝒙ᵢ are the 6 initial digits taken from the 6 calls to $RANDOM.

## Limitations:
Limitations
This method doesn't preclude the possibility of leading zeroes counting towards the 6-digit total.

