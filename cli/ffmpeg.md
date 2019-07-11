## Audio

### AAC encode

In VBR mode, 5 is higher bitrate than 4.

```
ffmpeg -i audio.wav -c:a libfdk_aac -vbr 4 output.m4a
ffmpeg -i audio.wav -c:a libfdk_aac -b:a 128k output.m4a

```

### Loudness (LUFS)

Analyse a file and determine the LUFS loudness, plus optionally the max
dBFS and true peak. Leave the `2> output-log.txt` off to just view the output
in the window.

```
ffmpeg -i audio.wav -af ebur128=peak=true -f null - 2> output-log.txt
ffmpeg -i audio.wav -af volumedetect,ebur128=peak=sample -f null - 2> output-log.txt
ffmpeg -i audio.wav -filter:a ebur128=peak=true -f null - 2> output-log.txt
```

## Webm

Encoding webm with VP9 and opus. It is a *very* slow encode. Example:

````
ffmpeg -i file.mp4 -c:v libvpx-vp9 -c:a libopus -b:a 96k -crf 32 -b:v 0 -deadline good -f webm output.webm
````