# Listen to a song from youtube

## Command:
```
$ listen-to-yt() { if [[ -z "$1" ]]; then echo "Enter a search string!"; else mpv "$(youtube-dl --default-search 'ytsearch1:' \"$1\" --get-url | tail -1)"; fi }
```

## Explanation:
Explanation
Firstly the function checks if user gave it any input, and notifies the user if they failed to do so.
If user has inputed a search string, the function will call upon youtube-dl to find url of the audio of the first matching youtube video and play that with mpv.
Call function by wrapping search string in quotes:
listen-to-yt "sultans of swing"
You have to paste the line in your .zshrc and source .zshrc for it to work.

## Limitations:
Limitations
The dependancies are youtube-dl and mpv.

