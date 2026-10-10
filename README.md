# Dolby-Vision-7.6-5.1-To-8.1-Converter
A tiny script using ffmeg, dovi_tool and mkvmerge to convert an MKV file from one DV profile to another.

**Dolby Vision 7.6 to 8.1**

```bat
ffmpeg.exe -i input.mkv -c:v copy -bsf:v hevc_mp4toannexb -f hevc - | dovi_tool.exe -m 2 convert --discard - -o temp.hevc 

mkvmerge.exe -o new.mkv temp.hevc --no-video input.mkv
```

- MKV input file name -> `input.mkv`
- Output mkv file -> `output.mkv`

Requires:
1. [FFMEG.exe](https://github.com/ffmpeg/ffmpeg)
2. [DOVI_TOOL.exe](https://github.com/quietvoid/dovi_tool)
3. [MKVMERGE.EXE](https://mkvtoolnix.org/)

to be in the same directory.

Does not clean up after itself, need to delete temp.hvec and input.mkv after running.
The new files take about the same size as the original MKV size.
