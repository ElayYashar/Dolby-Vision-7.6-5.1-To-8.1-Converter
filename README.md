# Dolby-Vision-7.6-5.1-To-8.1-Converter
A tiny script using ffmeg, dovi_tool and mkvmerge to convert an MKV file from one DV profile to another.

**Dolby Vision 7.6 to 8.1**

```bat
ffmpeg.exe -i input.mkv -c:v copy -bsf:v hevc_mp4toannexb -f hevc - | dovi_tool.exe -m 2 convert --discard - -o temp.hevc 

mkvmerge.exe -o new.mkv temp.hevc --no-video input.mkv
```
