---
layout: post
title: ffmpeg codes
tags: [collection]
---

1. batch to mp4
```
for %%a in ("*.*") do ffmpeg -i "%%a" -c:v copy -c:a aac -b:a 128k "newfiles\%%~na.mp4"
pause
```

2. combine to one
```
(for %%i in (*.mp4) do @echo file '%%i') > mylist.txt
ffmpeg -f concat -safe 0 -i mylist.txt -c copy myvideo.mp4
```

3. mp4 to mp3
```
for %%a in ("*.*") do ffmpeg -i "%%a" -acodec copy -vn "newfiles\%%~na.aac"
pause
```
```
for %%a in ("*.*") do ffmpeg -i "%%a" -acodec libmp3lame "newfiles\%%~na.mp3"
pause
```

4. adjust volume
```
for %%a in ("*.*") do ffmpeg -i "%%a" -c:v copy -af "volume=2" "newfiles\%%~na.mp4"
pause
```

5. capture
```
ffmpeg -i 0005.mp4 -f image2 -vf fps=fps=1/0.5 -qscale:v 2 mp4-%05d.jpg
```

6. screen size
(1)
```
ffmpeg -i 0005.mp4 -filter:v "pad=ih*16/9:ih:(ow-iw)/2:(oh-ih)/2" -c:a copy output.mp4
```
(2)
```
ffmpeg -i 0005.mp4 -vf scale=1920:1080 06.mp4
```

7. change audio
```
ffmpeg -i v.mp4 -i a.wav -c:v copy -map 0:v:0 -map 1:a:0 new.mp4
```