# Count the total number of hours of your music collection

## Command:
```
$ find . -print0 | xargs -0 -P 40 -n 1 sh -c 'ffmpeg -i "$1" 2>&1 | grep "Duration:" | cut -d " " -f 4 | sed "s/.$//" | tr "." ":"' - | awk -F ':' '{ sum1+=$1; sum2+=$2; sum3+=$3; sum4+=$4; if (sum4 > 100) { sum3+=1; sum4=0 }; if (sum3 > 60) { sum2+=1; sum3=0 }; if (sum2 > 60) { sum1+=1; sum2=0 } if (NR % 100 == 0) { printf "%.0f:%.0f:%.0f.%.0f\n", sum1, sum2, sum3, sum4 } } END { printf "%.0f:%.0f:%.0f.%.0f\n", sum1, sum2, sum3, sum4 }'
```

## Explanation:
Explanation
First the find command finds all files in your current directory (.). This is piped to xargs to be able to run the next shell pipeline in parallel.
The -P argument of xargs specifies how many processes to run in parallel. It's ok to set this higher than the number of your CPU cores, as the duration reading is mainly IO bound.
The -print0 and -0 arguments of find and xargs, respectively, are used to correctly handle files with spaces or other special characters.
A subshell is executed by xargs to have a shell pipeline for each file that is found by find. This pipeline extracts the duration and converts it to a format easily parsed by Awk.
ffmpeg reads the file and prints a lot of information about it, grep extracts the duration line. cut and sed cut out the time information, and tr converts . to : to make it easier to split by Awk.
Awk is a "pattern-directed scanning and processing language", often used in shell scripts for simple text processing. Here we use it to split the time elements into 4 variables and add them up. If one of the variables overflows (e.g. not more than 60 seconds per minute), the next one is incremented and that variable is reset to 0. Every 100 lines, the current values are printed, and at the end, they are printed again.

## Limitations:
Limitations
Requires ffmpeg, a stream audio and video processing tool.

