---
hide:
  - toc
---

#Requirements 

The Hand Tracking Tool is a web app limited to use open-source web technologies. For this reason, the application only works with videos encapsulated in ``.mp4`` or ``.webm`` formats, and encoded with ``h.264`` codec. 

If your video is already in ``.mp4`` or ``.webm`` formats, try to upload it to the web app. If there is no video displayed on the site, then you need to recode your video to ``h.264``.

There are many online tools to convert your video to ``h.264`` and save it in ``.mp4`` format. Including:

- [https://video-converter.com/](https://video-converter.com/)
- [Bear File Converter](https://www.ofoct.com/video-converter/convert-to-h-264-video.html)
- [Convert Files](https://www.convertfiles.com/convert/)

## Local processing

You can also recode your videos locally using [FFmpeg](https://ffmpeg.org/download.html). After installing the software, you can covert your files using the following command (in the command line or terminal):

```shell
ffmpeg -i INPUTFILE -vcodec libx264 -acodec copy OUTPUTFILE.mp4
```

For example, if your file is `myvideo.avi`, then your command shoud be 

```shell
ffmpeg -i myvideo.avi -vcodec libx264 -acodec copy myvideo.mp4
```

you migh also need to provide the file with a full path. 

### Improving video quality

If you would like to improve the resulting video quality, is possible to manipulate serveral FFmpeg parameters. In particular, you can modifidy parameters as `CRF` and `Preset`. 


>**CRF**:

>The range of the CRF scale is 0–51, where 0 is lossless (for 8 bit only, for 10 bit use -qp 0), 23 is the default, and 51 is worst quality possible. A lower value generally leads to higher quality, and a subjectively sane range is 17–28. Consider 17 or 18 to be visually lossless or nearly so; it should look the same or nearly the same as the input but it isn't technically lossless.

>The range is exponential, so increasing the CRF value +6 results in roughly half the bitrate / file size, while -6 leads to roughly twice the bitrate.

>Choose the highest CRF value that still provides an acceptable quality. If the output looks good, then try a higher value. If it looks bad, choose a lower value.


>**Preset**:

>A preset is a collection of options that will provide a certain encoding speed to compression ratio. A slower preset will provide better compression (compression is quality per filesize). This means that, for example, if you target a certain file size or constant bit rate, you will achieve better quality with a slower preset. Similarly, for constant quality encoding, you will simply save bitrate by choosing a slower preset.

>Use the slowest preset that you have patience for. The available presets in descending order of speed are:

>     - ultrafast
    - superfast
    - veryfast
    - faster
    - fast
    - medium – default preset
    - slow
    - slower
    - veryslow

More information can be found [here](https://trac.ffmpeg.org/wiki/Encode/H.264)


 
