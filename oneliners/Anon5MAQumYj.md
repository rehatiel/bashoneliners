# Anon5MAQumYj

## Command:
```
$ echo 'play alarmclock.wav 2>/dev/null' | at 07:30 tomorrow
```

## Explanation:
Explanation
at 07:30 tomorrow schedules a job for 7:30 AM the next day, running whatever command or script is fed to it as standard input.  The format for specifying time and date is rather flexible.  http://tinyurl.com/ibmdwat
echo 'play alarmclock.wav 2>/dev/null' | feeds the play alarmclock.wav command to at, while 2>/dev/null causes the text output of play to be thrown away (we are only interested in the alarm sound).

## Limitations:
No limitations specified

