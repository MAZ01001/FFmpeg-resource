# Some useful [FFmpeg](https://ffmpeg.org/ "Official FFmpeg website") commands

- [FFmpeg intro](#ffmpeg-intro "Scroll to this section")
  - [official documentation](#official-documentation "Scroll to this section")
  - [download FFmpeg](#download-ffmpeg "Scroll to this section")
  - [check configuration](#check-configuration "Scroll to this section")
    - [help/licence/version](#helplicenceversion "Scroll to this section")
    - [available/supported features](#availablesupported-features "Scroll to this section")
    - [restrict logging level](#restrict-logging-level "Scroll to this section")
  - [CLI controls](#cli-controls "Scroll to this section")
- [FFprobe file info](#ffprobe-file-info "Scroll to this section")
  - [Show/get stream metadata](#showget-stream-metadata "Scroll to this section")
- [FFplay video viewing](#ffplay-video-viewing "Scroll to this section")
  - [Watch a video (looping)](#watch-a-video-looping "Scroll to this section")
  - [Simulate Conway's game of life](#simulate-conways-game-of-life "Scroll to this section")
  - [FFplay video controls](#ffplay-video-controls "Scroll to this section")
- [FFmpeg video editing](#ffmpeg-video-editing "Scroll to this section")
  - [Convert MKV to MP4](#convert-mkv-to-mp4 "Scroll to this section")
  - [Convert MP4 to M4A (audio only mp4)](#convert-mp4-to-m4a-audio-only-mp4 "Scroll to this section")
  - [Edit metadata (add chapters)](#edit-metadata-add-chapters "Scroll to this section")
  - [Add thumbnail](#add-thumbnail "Scroll to this section")
  - [Add subtitles](#add-subtitles "Scroll to this section")
  - [Extract frames](#extract-frames "Scroll to this section")
  - [Create video from frames](#create-video-from-frames "Scroll to this section")
  - [crop video](#crop-video "Scroll to this section")
  - [scale video](#scale-video "Scroll to this section")
  - [compress video](#compress-video "Scroll to this section")
  - [cut video](#cut-video "Scroll to this section")
  - [loop video](#loop-video "Scroll to this section")
  - [Reverse video and/or Audio](#reverse-video-andor-audio "Scroll to this section")
  - [Concatenate multiple videos into one](#concatenate-multiple-videos-into-one "Scroll to this section")
    - [concat sections of videos](#concat-sections-of-videos "Scroll to this section")
  - [Create/download video with m3u8 playlist](#createdownload-video-with-m3u8-playlist "Scroll to this section")
  - [find silence parts in video](#find-silence-parts-in-video "Scroll to this section")
- [Libavfilter virtual input device (lavfi filtergraph)](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to this section")
  - [sierpinski (pan)](#sierpinski-pan "Scroll to this section")
  - [mandelbrot (zoom)](#mandelbrot-zoom "Scroll to this section")
  - [(elementary) cellular automaton](#elementary-cellular-automaton "Scroll to this section")
  - [life (Cellular automaton)](#life-cellular-automaton "Scroll to this section")
  - [mptestsrc (animated test patterns)](#mptestsrc-animated-test-patterns "Scroll to this section")
  - [empty (input)](#empty-input "Scroll to this section")
  - [color (input)](#color-input "Scroll to this section")
  - [smptebars (input)](#smptebars-input "Scroll to this section")
  - [smptehdbars (input)](#smptehdbars-input "Scroll to this section")
  - [testsrc (input)](#testsrc-input "Scroll to this section")
  - [testsrc2 (input)](#testsrc2-input "Scroll to this section")
  - [rgbtestsrc (input)](#rgbtestsrc-input "Scroll to this section")
  - [yuvtestsrc (input)](#yuvtestsrc-input "Scroll to this section")
  - [colorspectrum (input)](#colorspectrum-input "Scroll to this section")
  - [colorchart (input)](#colorchart-input "Scroll to this section")
  - [allrgb (input)](#allrgb-input "Scroll to this section")
  - [allyuv (input)](#allyuv-input "Scroll to this section")

> [!IMPORTANT]
>
> The order of (_some_) parameters/flags matters - before or after a given input or output (_FFmpeg supports multiple input files and [creating multiple output streams with one command](https://trac.ffmpeg.org/wiki/Creating%20multiple%20outputs "FFmpeg guide: Creating Multiple Outputs")_).

## FFmpeg intro

- [official documentation](#official-documentation "Scroll to this section")
- [download FFmpeg](#download-ffmpeg "Scroll to this section")
- [check configuration](#check-configuration "Scroll to this section")
  - [help/licence/version](#helplicenceversion "Scroll to this section")
  - [available/supported features](#availablesupported-features "Scroll to this section")
  - [restrict logging level](#restrict-logging-level "Scroll to this section")
- [CLI controls](#cli-controls "Scroll to this section")

Scroll [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### official documentation

- Full FFmpeg documentation @ <https://ffmpeg.org/ffmpeg-all.html> ([archive](https://web.archive.org/web/*/https://ffmpeg.org/ffmpeg-all.html "waybackmachine (overview)"))
- Full FFplay documentation @ <https://ffmpeg.org/ffplay-all.html> ([archive](https://web.archive.org/web/*/https://ffmpeg.org/ffplay-all.html "waybackmachine (overview)"))
- Full FFprobe documentation @ <https://ffmpeg.org/ffprobe-all.html> ([archive](https://web.archive.org/web/*/https://ffmpeg.org/ffprobe-all.html "waybackmachine (overview)"))

Scroll [UP](#ffmpeg-intro "Scroll to beginning of FFmpeg intro section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### download FFmpeg

Get FFmpeg from <https://ffmpeg.org/download.html>

I currently use the FFmpeg builds from <https://www.gyan.dev/ffmpeg/builds/> (for Windows 7+)
under the __release builds__ section the file `ffmpeg-release-full.7z`
or directly <https://www.gyan.dev/ffmpeg/builds/ffmpeg-release-full.7z>
(_don't forget [7-Zip](https://www.7-zip.org/ "Official 7-Zip homepage") for unpacking the `.7z` file_)

Scroll [UP](#ffmpeg-intro "Scroll to beginning of FFmpeg intro section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### check configuration

- [help/licence/version](#helplicenceversion "Scroll to this section")
- [available/supported features](#availablesupported-features "Scroll to this section")
- [restrict logging level](#restrict-logging-level "Scroll to this section")

> see [Generic options](https://ffmpeg.org/ffmpeg-all.html#Generic-options "FFmpeg documentation: Generic options")

Scroll [UP](#ffmpeg-intro "Scroll to beginning of FFmpeg intro section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

#### help/licence/version

```shell
ffmpeg -h       # CLI help
ffmpeg -L       # FFmpeg licence
ffmpeg -version # FFmpeg build version
```

Scroll [UP](#check-configuration "Scroll to beginning of check configuration section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

#### available/supported features

```shell
ffmpeg -buildconf    # FFmpeg build configuration
ffmpeg -formats      # files (and devices) de-/muxing support
ffmpeg -pix_fmts     # pixel formats (in/out/hardware acceleration/palette/bitstream)
ffmpeg -protocols    # protocols (in/out) like: file, https, sftp
ffmpeg -codecs       # video/audio/subtitle/data en-/decoders (also shows if lossy or lossless)
ffmpeg -filters      # video/audio (libavfilter) filters like: avgblur V->V (video in; video out)
ffmpeg -bsfs         # bitstream filters like: null, h264_metadata, hevc_metadata
ffmpeg -dispositions # how a stream is added to an output file; for example attached_pic is the file thumbnail/cover art for video files like MP4 (visible in file explorer)
ffmpeg -colors       # color names with their hex value; for example: Lime #00ff00
```

Scroll [UP](#check-configuration "Scroll to beginning of check configuration section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

#### restrict logging level

```shell
ffmpeg -hide_banner     # does not log version/copyright/buildconfig
ffmpeg -v level+warning # only log warnings and worse and shows level: "[warning] ..."
                        # debug > verbose > info (default) > warning > error > fatal > quiet (nothing)
                        # banner is info so -hide_banner is not needed with warning or less
ffmpeg -stats           # allways show stats (en-/decoding progress), even when log level is less than info
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")

Scroll [UP](#check-configuration "Scroll to beginning of check configuration section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### CLI controls

CLI keyboard hotkeys mid-process:

| key          | function                                             |
| ------------ | ---------------------------------------------------- |
| <kbd>?</kbd> | show this table                                      |
| <kbd>+</kbd> | increase verbosity (logging level)                   |
| <kbd>-</kbd> | decrease verbosity (logging level)                   |
| <kbd>q</kbd> | quit                                                 |
| <kbd>c</kbd> | Send command to first matching filter supporting it  |
| <kbd>C</kbd> | Send/Queue command to all matching filters           |
| <kbd>D</kbd> | cycle through available debug modes                  |
| <kbd>h</kbd> | dump packets/hex press to cycle through the 3 states |
| <kbd>s</kbd> | Show QP histogram                                    |

_I didn't find an official documentation for these..._

Scroll [UP](#ffmpeg-intro "Scroll to beginning of FFmpeg intro section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

## FFprobe file info

- [Show/get stream metadata](#showget-stream-metadata "Scroll to this section")

Scroll [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### Show/get stream metadata

_Output of the following commands is going to stdout (standard output), if no `-o OUTPUT.log` is specified_

```shell
# list all audio streams and their language-tag (if set) in compact format (seperator ":", no field-names, and ommit section name)
ffprobe -v level+warning -i INPUT.mp4 -show_entries stream=index:stream_tags=language -select_streams a -of compact=s=\::nk=1:p=0
# [stream_index]:[tag_language]
# 1:eng
```

> [!NOTE]
>
> FFprobe uses 3 letter [__ISO 639-2__](https://en.wikipedia.org/wiki/List_of_ISO_639-2_codes#iso-codes "Wikipedia: List of ISO 639-2 codes") language codes

---

```shell
# list all streams with index, codec_name, codec_type, and language-tag (if set) in compact format (seperator ":", no field-names, and ommit section name)
ffprobe -v level+warning -i INPUT.mp4 -show_entries stream=index,codec_type,codec_name:stream_tags=language -of compact=s=\::nk=1:p=0
# [stream_index]:[codec_name]:[codec_type]:[tag_language]
# 0:h264:video:und  (undetermined)
# 1:aac:audio:eng
# 2:png:video       (DISPOSITION:attached_pic ie the file thumbnail)
```

> see how to [Add thumbnail](#add-thumbnail "Scroll to this section")

---

```shell
# show all chapters (if any) of this file with id, start_time, end_time, and title (time in seconds) in compact format (seperator ":", no field-names, and ommit section name)
ffprobe -v level+warning -i INPUT.mp4 -show_entries chapter=id,start_time,end_time:chapter_tags=title -of compact=s=\::nk=1:p=0
# [chapter_id]:[start_time]:[end_time]:[chapter_title]
# 0:0.000000:10.000000:First 10 seconds
# 1:60.000000:120.000000:Second minute
```

> see how to [Edit metadata (add chapters)](#edit-metadata-add-chapters "Scroll to this section")

---

```shell
# most relevant metadata in JSON format (secify output file instead of stdout)
ffprobe -v level+warning -i INPUT.mp4 -o OUTPUT.json -show_entries stream=index,codec_type,codec_name,width,height,display_aspect_ratio,avg_frame_rate,start_time,duration,bit_rate,sample_rate,channels,channel_layout:stream_tags=language,title:stream_disposition:chapter=id,start_time,end_time:chapter_tags=title:format=filename,duration,size,bit_rate:format_tags=title,artist,date,comment -of json
# see JSON structure with type info and some extra notes below
```

<details><summary>Click to show <code>-show_entries</code> value with added whitespace for readability</summary>

```text
stream        = index, codec_type, codec_name, width, height, display_aspect_ratio, avg_frame_rate,
                start_time, duration, bit_rate, sample_rate, channels, channel_layout:
stream_tags   = language , title:
stream_disposition:
chapter       = id, start_time, end_time:
chapter_tags  = title:
format        = filename,duration, size, bit_rate:
format_tags   = title, artist, date, comment
```

</details>

<details><summary>Click to show JSON format/type info (only for above command)</summary>

_Not a general list of keys, just those that are output by the above command_

```typescript
type FFprobeJSON = {
  programs: never[];              // (all via -show_programs)
  stream_groups: never[];         // (all via -show_stream_groups)
  streams: {                      // (all via -show_streams)
    index: number;
    codec_name: string;           // "h264"/"png"/"aac"/...
    codec_type: string;           // "video"/"audio"/...
    width: number;
    height: number;
    display_aspect_ratio: string; // usually "16:9"
    avg_frame_rate: string;
    start_time: string;           // time in seconds
    duration: string;             // time in seconds
    bit_rate: string;
    disposition: {                // only one should be 1 (if any)
      default: 0|1;
      dub: 0|1;
      original: 0|1;
      comment: 0|1;
      lyrics: 0|1;
      karaoke: 0|1;
      forced: 0|1;
      hearing_impaired: 0|1;
      visual_impaired: 0|1;
      clean_effects: 0|1;
      attached_pic: 0|1;          // for cover-images/file-thubnails
      timed_thumbnails: 0|1;
      non_diegetic: 0|1;
      captions: 0|1;
      descriptions: 0|1;
      metadata: 0|1;
      dependent: 0|1;
      still_image: 0|1;
      multilayer: 0|1;
    };
    tags: {
      language: string;           // 3 letter (ISO 639-2) language tag
      title: string;
    };
    sample_rate: string;
    channels: number;             // usually 2 for audio streams (left right)
    channel_layout: string;       // usually stereo for audio streams
  }[];
  chapters: {                     // (all via -show_chapters)
    id: number;
    start_time: string;           // time in seconds
    end_time: string;             // time in seconds
    tags: {
      title: string;              // name of chapter
    };
  }[];
  format: {                       // (all via -show_format)
    filename: string;             // exact path/URL given to FFprobe
    duration: string;             // entire file duration in seconds
    size: string;                 // file size in bytes
    bit_rate: string;
    tags: {
      title: string;
      artist: string;
      date: string;
      comment: string;
    };
  };
};
```

</details>

---

Also, custom [metadata](https://ffmpeg.org/ffprobe-all.html#Metadata "Documentation of general Metadata info") added via [`-metadata field=value`](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dmetadata%5B%3Ametadata_specifier%5D%20key%3Dvalue%20(output%2Cper%2Dmetadata) "FFmpeg documentation of `-metadata[:metadata_specifier] key=value (output,per-metadata)`")
can be read with `-show_entries format_tags=field` (then `{}.format.tags.field` (string) in JSON) or within `-show_format` as `TAG:field=value` (if no output format was specified; value may span multiple lines)

_Keep in mind that whitespace will not be ignored, so `-metadata "field = data"` has key "field " and value " data"_

- [`-v` documentation](https://ffmpeg.org/ffprobe-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-i` documentation](https://ffmpeg.org/ffprobe-all.html#:~:text=%2Di%20input_url "Documentation of `-i input_url`")
- [`-o` documentation](https://ffmpeg.org/ffprobe-all.html#:~:text=%2Do%20output_url "Documentation of `-o output_url`")
- [`-show_entries` documentation](https://ffmpeg.org/ffprobe-all.html#:~:text=%2Dshow_entries%20section_entries "Documentation of `-show_entries section_entries`")
- [`-select_streams` documentation](https://ffmpeg.org/ffprobe-all.html#:~:text=%2Dselect_streams%20stream_specifier "Documentation of `-select_streams stream_specifier`")
- [`-of` documentation](https://ffmpeg.org/ffprobe-all.html#:~:text=%2Doutput_format%2C%20%2Dof%2C%20%2Dprint_format%20writer_name%5B%3Dwriter_options%5D "Documentation of `-output_format, -of, -print_format writer_name[=writer_options]`")
  - [`compact` documentation](https://ffmpeg.org/ffprobe-all.html#compact_002c-csv "Documentation of `compact, csv`")
  - [`json` documentation](https://ffmpeg.org/ffprobe-all.html#json "Documentation of `json`")
- [`-show_programs` documentation](https://ffmpeg.org/ffprobe-all.html#:~:text=%2Dshow_programs "Documentation of `-show_programs`")
- [`-show_stream_groups` documentation](https://ffmpeg.org/ffprobe-all.html#:~:text=%2Dshow_stream_groups "Documentation of `-show_stream_groups`")
- [`-show_streams` documentation](https://ffmpeg.org/ffprobe-all.html#:~:text=%2Dshow_streams,-Show "Documentation of `-show_streams`")
- [`-show_chapters` documentation](https://ffmpeg.org/ffprobe-all.html#:~:text=%2Dshow_chapters "Documentation of `-show_chapters`")
- [`-show_format` documentation](https://ffmpeg.org/ffprobe-all.html#:~:text=%2Dshow_format "Documentation of `-show_format`")

Scroll [UP](#ffprobe-file-info "Scroll to beginning of FFprobe section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

## FFplay video viewing

- [Watch a video (looping)](#watch-a-video-looping "Scroll to this section")
- [Simulate Conway's game of life](#simulate-conways-game-of-life "Scroll to this section")
- [FFplay video controls](#ffplay-video-controls "Scroll to this section")

Scroll [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### Watch a video (looping)

```shell
ffplay -v level+warning -stats -loop -1 INPUT.mp4
```

A window will show the video looping infinitly (see [FFplay video controls](#ffplay-video-controls "Scroll to this section"))

- [`-v` documentation](https://ffmpeg.org/ffplay-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffplay-all.html#:~:text=%2Dstats,-Print%20several%20playback%20statistics "Documentation of `-stats`")
- [`-loop` documentation](https://ffmpeg.org/ffplay-all.html#:~:text=-loop%20number,-Loops%20movie%20playback "Documentation of `-loop number`")

Scroll [UP](#ffplay-video-viewing "Scroll to beginning of FFplay section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### Simulate Conway's game of life

```shell
# random simulation, window size 1280*960 (4 times 320*240, which is the default size)
ffplay -v level+warning -stats -f lavfi life=mold=25:life_color=\#00ff00:death_color=\#aa0000,scale=4*iw:-1:flags=neighbor
```

A window will show the simulation infinitly (see [FFplay video controls](#ffplay-video-controls "Scroll to this section"))

> [!NOTE]
>
> seeking is not available, only pause/resume or frame-by-frame playback

- [`-v` documentation](https://ffmpeg.org/ffplay-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffplay-all.html#:~:text=%2Dstats,-Print%20several%20playback%20statistics "Documentation of `-stats`")
- see [life (cellular automaton)](#life-cellular-automaton "Scroll to this section") section below
- [`scale` filter documentation](https://ffmpeg.org/ffmpeg-all.html#scale "Documentation of `scale` filter")
  - [`flags` option (scaler options: `sws_flags`) scaling algorithm](https://ffmpeg.org/ffmpeg-all.html#sws_005fflags "Documentation of `sws_flags` scaling algorithms (`scale` filter uses these for its `flags` option)")

Scroll [UP](#ffplay-video-viewing "Scroll to beginning of FFplay section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### FFplay video controls

> <https://ffmpeg.org/ffplay-all.html#While-playing>

| Key                                                        | Action                                                 |
| ---------------------------------------------------------- | ------------------------------------------------------ |
| <kbd>Q</kbd> / <kbd>ESC</kbd>                              | Quit                                                   |
| <kbd>F</kbd> or <kbd>left mouse double-click</kbd>         | Toggle full screen                                     |
| <kbd>P</kbd> / <kbd>SPACE</kbd>                            | Pause/Resume                                           |
| <kbd>S</kbd>                                               | Step to next frame (and pause) `frame-by-frame`        |
| <kbd>←</kbd> / <kbd>→</kbd>                                | Seek back-/forward 10 seconds                          |
| <kbd>↓</kbd> / <kbd>↑</kbd>                                | Seek back-/forward 1 minute                            |
| <kbd>PAGE DOWN</kbd> / <kbd>PAGE UP</kbd>                  | Seek to the previous/next chapter (or 10 minutes)      |
| <kbd>right mouse click</kbd>                               | Seek to percentage by click position (of window width) |
| <kbd>9</kbd> / <kbd>0</kbd> or <kbd>/</kbd> / <kbd>*</kbd> | De-/increase volume                                    |
| <kbd>M</kbd>                                               | Toggle mute                                            |
| <kbd>A</kbd>                                               | Cycle audio channel (current program)                  |
| <kbd>T</kbd>                                               | Cycle subtitle channel (current program)               |
| <kbd>C</kbd>                                               | Cycle program                                          |
| <kbd>V</kbd>                                               | Cycle video channel                                    |
| <kbd>W</kbd>                                               | Cycle video filter/show modes                          |

## FFmpeg video editing

- [Convert MKV to MP4](#convert-mkv-to-mp4 "Scroll to this section")
- [Convert MP4 to M4A (audio only mp4)](#convert-mp4-to-m4a-audio-only-mp4 "Scroll to this section")
- [Edit metadata (add chapters)](#edit-metadata-add-chapters "Scroll to this section")
- [Add thumbnail](#add-thumbnail "Scroll to this section")
- [Add subtitles](#add-subtitles "Scroll to this section")
- [Extract frames](#extract-frames "Scroll to this section")
- [Create video from frames](#create-video-from-frames "Scroll to this section")
- [crop video](#crop-video "Scroll to this section")
- [scale video](#scale-video "Scroll to this section")
- [compress video](#compress-video "Scroll to this section")
- [cut video](#cut-video "Scroll to this section")
- [loop video](#loop-video "Scroll to this section")
- [Reverse video and/or Audio](#reverse-video-andor-audio "Scroll to this section")
- [Concatenate multiple videos into one](#concatenate-multiple-videos-into-one "Scroll to this section")
  - [concat sections of videos](#concat-sections-of-videos "Scroll to this section")
- [Create/download video with m3u8 playlist](#createdownload-video-with-m3u8-playlist "Scroll to this section")
- [find silence parts in video](#find-silence-parts-in-video "Scroll to this section")

Scroll [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### Convert MKV to MP4

the mkv video file format is suggested when streaming or recording (via OBS) since it can be easily recovert

```shell
# Audio codec already is AAC, so it can be copied to save some time
# Also use some compression to shrink the file size a bit
ffmpeg -v level+warning -stats -i INPUT.mkv -c:a copy -c:v libx264 -crf 12 OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-c` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dc%5B%3Astream_specifier%5D%20codec%20(input/output%2Cper%2Dstream) "Documentation of `-c[:stream_specifier] codec (input/output,per-stream)`")
  - [Stream specifiers documentation](https://ffmpeg.org/ffmpeg-all.html#Stream-specifiers "Documentation of stream specifiers for `-c`")
- [`-crf` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=crf,-Set%20the%20quality/size%20tradeoff%20for%20constant%2Dquality "Documentation of `-crf`") (the best description is under libaom-AV1 but it's also in other encoders like MPEG-4)
- also see [this guide](https://trac.ffmpeg.org/wiki/Encode/H.264#crf "H.264 Video Encoding Guide") for CRF with `libx264`

Scroll [UP](#ffmpeg-video-editing "Scroll to beginning of FFmpeg section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### Convert MP4 to M4A (audio only mp4)

only include audio and subtitles (if present)

```shell
ffmpeg -v level+warning -stats -i INPUT.mp4 -c copy -map 0:a -map 0:s? OUTPUT.m4a
```

or only exclude video

```shell
ffmpeg -v level+warning -stats -i INPUT.mp4 -c copy -map 0 -map -0:v OUTPUT.m4a
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-c` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dc%5B%3Astream_specifier%5D%20codec%20(input/output%2Cper%2Dstream) "Documentation of `-c[:stream_specifier] codec (input/output,per-stream)`")
  - [Stream specifiers documentation](https://ffmpeg.org/ffmpeg-all.html#Stream-specifiers "Documentation of stream specifiers for `-c`")
- [`-map` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dmap%20%5B%2D%5Dinput_file_id%5B%3Astream_specifier%5D%5B%3F%5D%20%7C%20%5Blinklabel%5D%20(output) "Documentation of `-map [-]input_file_id[:stream_specifier][?] | [linklabel] (output)`")

Scroll [UP](#ffmpeg-video-editing "Scroll to beginning of FFmpeg section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### Edit metadata (add chapters)

export all metadata to a file

```shell
ffmpeg -v level+warning -stats -i INPUT.mp4 -f ffmetadata FFMETADATAFILE.txt
```

it looks something like this

```ini
;FFMETADATA1

# empty lines or lines starting with ; or # will be ignored
# whitespace will not be ignored so "title = A" would be interpreted as key "title " and value " A"

title=Video Title
artist=Artist Name

# newlines and other special characters like = ; # \ must be escaped with a \
description=Text\
Line two\
\
\
Line five\
Line with Û̕͝͡n̊̑̓̊i͚͚ͬ́c̗͕̈́̀o̵̯ͣ͊ḑ̴̱̐ḛ̯̓̒

# then adding chapters is very simple | order does not matter (no intersection ofc), so easiest is to append them to the end of file

[CHAPTER]
# fractions of a second so 1/1000 says the following START and END are in milliseconds
TIMEBASE=1/1000
# start and end might change a bit when reinserting (snaps to nearest frame when video stream is copied and not encoded)
START=0
END=10000
title=0 to 10sec of the video

[CHAPTER]
TIMEBASE=1/1000
START=10000
END=20000
title=10sec to 20sec of the video
```

then to reinsert the edited metadata file

```shell
ffmpeg -v level+warning -stats -i INPUT.mp4 -i FFMETADATAFILE.txt -map_metadata 1 -c copy OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [full metadata documentation](https://ffmpeg.org/ffmpeg-all.html#Metadata-1 "A little more detailed documentation as seen above")
- You might also want to look at the [`-metadata` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dmetadata%5B%3Ametadata_specifier%5D%20key%3Dvalue%20(output%2Cper%2Dmetadata) "Documentation of `-metadata[:metadata_specifier] key=value (output,per-metadata)`")

Scroll [UP](#ffmpeg-video-editing "Scroll to beginning of FFmpeg section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### Add thumbnail

```shell
ffmpeg -v level+warning -stats -i INPUT.mp4 -i IMAGE.png -map 0 -map 1 -c copy -c:v:1 png -disposition:v:1 attached_pic OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-c` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dc%5B%3Astream_specifier%5D%20codec%20(input/output%2Cper%2Dstream) "Documentation of `-c[:stream_specifier] codec (input/output,per-stream)`")
  - [Stream specifiers documentation](https://ffmpeg.org/ffmpeg-all.html#Stream-specifiers "Documentation of stream specifiers for `-c`")
- [`-map` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dmap%20%5B%2D%5Dinput_file_id%5B%3Astream_specifier%5D%5B%3F%5D%20%7C%20%5Blinklabel%5D%20(output) "Documentation of `-map [-]input_file_id[:stream_specifier][?] | [linklabel] (output)`")
- [`-disposition` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Ddisposition%5B%3Astream_specifier%5D%20value%20(output%2Cper%2Dstream) "Documentation of `-disposition[:stream_specifier] value (output,per-stream)`")
- [How To add an embedded cover/thumbnail](https://ffmpeg.org/ffmpeg-all.html#:~:text=To%20add%20an%20embedded%20cover/thumbnail%3A "Example of how to add an embedded cover/thumbnail (with `-disposition`)") (within the `-disposition` documentation)

Scroll [UP](#ffmpeg-video-editing "Scroll to beginning of FFmpeg section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### Add subtitles

Adding subtitles as an extra stream so they can be turned on and off.

_Needs a video player that supports this feature like [VLC](https://www.videolan.org/vlc/ "Official VLC website")._

```shell
# for mkv output
ffmpeg -v level+warning -stats -i INPUT.mp4 -i SUB.srt -c copy OUTPUT.mkv

# for mp4 output
ffmpeg -v level+warning -stats -i INPUT.mp4 -i SUB.srt -c copy -c:s mov_text OUTPUT.mp4

# ... with multiple subtitle files
ffmpeg -v level+warning -stats -i INPUT.mp4 -i SUB_ENG.srt -i SUB_GER.srt -map 0:0 -map 1:0 -map 2:0 -c copy -c:s mov_text OUTPUT.mp4

# ... with language codes
ffmpeg -v level+warning -stats -i INPUT.mp4 -i SUB_ENG.srt -i SUB_GER.srt -map 0:0 -map 1:0 -map 2:0 -c copy -c:s mov_text -metadata:s:s:0 language=eng -metadata:s:s:1 language=ger OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-c` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dc%5B%3Astream_specifier%5D%20codec%20(input/output%2Cper%2Dstream) "Documentation of `-c[:stream_specifier] codec (input/output,per-stream)`")
  - [Stream specifiers documentation](https://ffmpeg.org/ffmpeg-all.html#Stream-specifiers "Documentation of stream specifiers for `-c`")
- [`-map` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dmap%20%5B%2D%5Dinput_file_id%5B%3Astream_specifier%5D%5B%3F%5D%20%7C%20%5Blinklabel%5D%20(output) "Documentation of `-map [-]input_file_id[:stream_specifier][?] | [linklabel] (output)`")
- [`-metadata` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dmetadata%5B%3Ametadata_specifier%5D%20key%3Dvalue%20(output%2Cper%2Dmetadata) "Documentation of `-metadata[:metadata_specifier] key=value (output,per-metadata)`")

A subtitle file (`.srt`) may look like this:

```SRecode-Template
1
00:00:00,000 --> 00:00:03,000
hello there

2
00:00:04,000 --> 00:00:08,000
general kenobi

3
00:00:10,000 --> 00:01:00,000
multi
line
subtitles
```

displayed like in file → new line in SRT = new line in video

Unicode can be used → tested with z̵̢͎̟͛ͥ̄͑̐͐a̡͈̳̟ͧ̑̓͆̔ͬl̗̠̭͖͓͚ͭ̐͊͊ģ͖͈̍̓ͭͩ̚͝͞ơ̢̞̫̜̞̓͗͊ͪ text and it "pushed" the subtitles of screen (big line height)

> [!NOTE]
>
> Not all subtitle files are [supported by FFmpeg](https://ffmpeg.org/ffmpeg-all.html#Subtitle-Formats "List of Supported subtitle formats (FFmpeg wiki)").

Scroll [UP](#ffmpeg-video-editing "Scroll to beginning of FFmpeg section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### Extract frames

```shell
# dump ALL frames
ffmpeg -v level+warning -stats -i INPUT.mp4 ./_dump/frame%03d.png

# dump frames with custom frame rate (here 1fps)
ffmpeg -v level+warning -stats -i INPUT.mp4 -r 1 ./_dump/frame%03d.png

# dump custom number of frames
ffmpeg -v level+warning -stats -i INPUT.mp4 -frames:v 3 ./_dump/frame%03d.png

# dump all frames in a timeframe (here from 0:00:02 to 0:00:05)
ffmpeg -v level+warning -stats -ss 2 -i INPUT.mp4 -t 3 ./_dump/frame%03d.png
ffmpeg -v level+warning -stats -ss 2 -i INPUT.mp4 -to 5 ./_dump/frame%03d.png
```

> [!IMPORTANT]
>
> The directory path must exist, ie, folders must be created beforehand.

- `png` is a good middle ground (lossless compression, but supports less colors)
- `jpeg` is slower but has good compression (lossy compression)
- `bmp` is faster but has large file size (uncompressed)

The format `frame%03d.png` means files will be named: `frame001.png`, `frame002.png`, ..., `frame050.png`, ..., `frame1000.png`, and so on

> [!TIP]
>
> use `-start_number 0` (before output) to start at `frame000.png`

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [image file muxer (output)](https://ffmpeg.org/ffmpeg-all.html#image2_002c-image2pipe "Documentation for outputting images")
- [`-r` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dr%5B%3Astream_specifier%5D%20fps%20(input/output%2Cper%2Dstream) "Documentation of `-r[:stream_specifier] fps (input/output,per-stream)`")
- [`-ss` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dss%20position%20(input/output) "Documentation of `-ss position (input/output)`")
- [`-t` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dt%20duration%20(input/output) "Documentation of `-t duration (input/output)`")
- [`-to` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dto%20position%20(input/output) "Documentation of `-to position (input/output)`")

`-ss`, `-t`, and `-to` expect a specific [time format](https://ffmpeg.org/ffmpeg-all.html#Time-duration "Documentation for time duration format")
in short `[-][HH:]MM:SS[.m...]` or `[-]S+[.m...][s|ms|us]`

Scroll [UP](#ffmpeg-video-editing "Scroll to beginning of FFmpeg section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### Create video from frames

```shell
# uses files INPUT000.png, INPUT001.png, etc to create the mp4 video (with 24fps)
ffmpeg -v level+warning -stats -framerate 24 -i INPUT%03d.png OUTPUT.mp4

# uses every png file that starts with INPUT (at 24fps)
ffmpeg -v level+warning -stats -framerate 24 -i INPUT*.png OUTPUT.mp4

# uses every png file (at 24fps)
ffmpeg -v level+warning -stats -framerate 24 -i *.png OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [image file demuxer (input)](https://ffmpeg.org/ffmpeg-all.html#image2-1 "Documentation for inputting images")
- [`-framerate` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dframerate,-Set%20the%20grabbing%20frame%20rate. "Documentation of `-framerate`")

Scroll [UP](#ffmpeg-video-editing "Scroll to beginning of FFmpeg section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### crop video

```shell
ffmpeg -v level+warning -stats -i INPUT.mp4 -vf crop=WIDTH:HEIGHT:POSX:POSY OUTPUT.mp4
```

- `WIDTH` - the width of the croped window
- `HEIGHT` - the height of the croped window
- `POSX` - the X position of the croped window (can be omitted = auto center)
- `POSY` - the Y position of the croped window (can be omitted = auto center)
- all values are in pixels, but there is no "px" after it (or an expression that gets calculated each frame)

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [full crop filter documentation](https://ffmpeg.org/ffmpeg-all.html#crop "Documentation for the crop filter")

Scroll [UP](#ffmpeg-video-editing "Scroll to beginning of FFmpeg section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### scale video

```shell
# scale to WIDTH*HEIGHT (stretches to new resolution)
ffmpeg -v level+warning -stats -i INPUT.mp4 -vf "scale=WIDTH:HEIGHT" OUTPUT.mp4

# preserve aspect ratio with letter-/pillarbox (black bars)
ffmpeg -v level+warning -stats -i INPUT.mp4 -vf "scale=WIDTH:HEIGHT:force_original_aspect_ratio=decrease,pad=WIDTH:HEIGHT:POSX:POSY,setsar=1" OUTPUT.mp4
```

- `WIDTH` - the width of the desired output resolution
- `HEIGHT` - the height of the desired output resolution
- `POSX` - the X position of the video in the padding region (`-1` to auto center; default is `0`)
- `POSY` - the Y position of the video in the padding region (`-1` to auto center; default is `0`)
- all values are in pixels, but there is no "px" after it (or an expression that gets calculated each frame, like `(ow-iw)/2` for `POSX` to center horizontally)

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [simple filtergraphs documentation](https://ffmpeg.org/ffmpeg-all.html#Simple-filtergraphs "Documentation for simple filtergraphs (like `-filter:v`/`-vf`)")
  - [scale filter documentation](https://ffmpeg.org/ffmpeg-all.html#scale-1 "Documentation for the scale filter")
    - [scaler options](https://ffmpeg.org/ffmpeg-all.html#Scaler-Options "Documentation for scaler options")
  - [pad filter documentation](https://ffmpeg.org/ffmpeg-all.html#pad-1 "Documentation for the pad filter")
  - [setsar filter documentation](https://ffmpeg.org/ffmpeg-all.html#setdar_002c-setsar "Documentation for the setsar filter")

Scroll [UP](#ffmpeg-video-editing "Scroll to beginning of FFmpeg section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### compress video

lower values are better (higher bitrate), but also lead to larger file size

```shell
# for `h.264` values from 18 to 23 are very good
ffmpeg -v level+warning -stats -i INPUT.mp4 -c copy -c:v libx264 -crf 20 OUTPUT.mp4

# for `h.265` values from 24 to 30 are very good
ffmpeg -v level+warning -stats -i INPUT.mp4 -c copy -c:v libx265 -crf 25 OUTPUT.mp4
```

faster with GPU hardware acceleration / NVIDIA CUDA

```shell
# for h.264 → h264_nvenc with NVIDIA CUDA
ffmpeg -v level+warning -stats -hwaccel cuda -hwaccel_output_format cuda -i INPUT.mp4 -c copy -c:v h264_nvenc -fps_mode passthrough -b_ref_mode disabled -preset medium -tune hq -rc vbr -multipass disabled -qp 20 OUTPUT.mp4

# for h.265 → hevc_nvenc with NVIDIA CUDA
ffmpeg -v level+warning -stats -hwaccel cuda -hwaccel_output_format cuda -i INPUT.mp4 -c copy -c:v hevc_nvenc -fps_mode passthrough -b_ref_mode disabled -preset medium -tune hq -rc vbr -multipass disabled -qp 25 OUTPUT.mp4
```

and even better by specifying the (output) bitrate manually

```shell
# for h.264 → h264_nvenc with NVIDIA CUDA
# bitrate ~ 4M with limit 500k - 8M and buffer size 8M (should be larger than input video bitrate)
# and QP 4 (high quality/less lossy compression)
ffmpeg -v level+warning -stats -hwaccel cuda -hwaccel_output_format cuda -i INPUT.mp4 -c copy -c:v h264_nvenc -preset p7 -tune hq -profile:v high -level:v auto -rc vbr -b:v 4M -minrate:v 500k -maxrate:v 8M -bufsize:v 8M -multipass disabled -fps_mode passthrough -b_ref_mode:v disabled -rc-lookahead:v 32 -qp 4 OUTPUT.mp4
```

<details closed><summary>Click to show formatted codec arguments from last command above</summary>

```text
- c copy

-c:v h264_nvenc
-preset p7
-tune hq
-profile:v high
-level:v auto

-rc vbr

-b:v 4M
-minrate:v 500k
-maxrate:v 8M
-bufsize:v 8M

-multipass disabled
-fps_mode passthrough
-b_ref_mode:v disabled
-rc-lookahead:v 32

-qp 4
```

</details>

> [!NOTE]
>
> also, note that if there is an `attached_pic` (ie [file thumbnail](#add-thumbnail "Scroll to the section for how to add a file thumbnail on this page")), then the `:v` stream specifier will also include it and thus tries to encode with NVENC, which will give an error, so instead you'll need to specify further which video stream to encode
>
> by adding `-map 0` before the `-c copy` to copy over every stream (of first input) and disposition (thus also the `attached_pic`) and then `:v:0` to select the first video stream as the one to encode with NVENC

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-map` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dmap%20%5B%2D%5Dinput_file_id%5B%3Astream_specifier%5D%5B%3F%5D%20%7C%20%5Blinklabel%5D%20(output) "Documentation of `-map [-]input_file_id[:stream_specifier][?] | [linklabel] (output)`")
- [`-c` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dc%5B%3Astream_specifier%5D%20codec%20(input/output%2Cper%2Dstream) "Documentation of `-c[:stream_specifier] codec (input/output,per-stream)`")
  - [Stream specifiers documentation](https://ffmpeg.org/ffmpeg-all.html#Stream-specifiers "Documentation of stream specifiers for `-c`")
- [`-crf` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=crf,-Set%20the%20quality/size%20tradeoff%20for%20constant%2Dquality "Documentation of `-crf`") (the best description is under libaom-AV1 but it's also in other encoders like MPEG-4)
  - also see [this FFmpeg guide](https://trac.ffmpeg.org/wiki/Encode/H.264#crf "H.264 Video Encoding Guide") for CRF with `libx264`
  - CUDA ignores [`-crf`](https://ffmpeg.org/ffmpeg-all.html#:~:text=crf,-Set%20the%20quality/size%20tradeoff%20for%20constant%2Dquality "Documentation of `-crf`") (the best description is under libaom-AV1 but it's also in other encoders like MPEG-4) so it's `-qp` for the hardware acceleration
- also ["this FFmpeg guide"](https://trac.ffmpeg.org/wiki/HWAccelIntro#CUDANVENCNVDEC "CUDA (NVENC/NVDEC) section of Hardware Acceleration Intro") for hardware acceleration with differend OS/hardware (specifically section _CUDA (NVENC/NVDEC)_)
  - and ["Using FFmpeg with NVIDIA GPU Hardware Acceleration"](https://docs.nvidia.com/video-technologies/video-codec-sdk/12.0/ffmpeg-with-nvidia-gpu/ "NVIDIA Documentation Hub: Using FFmpeg with NVIDIA GPU Hardware Acceleration") on the NVIDIA Documentation Hub

Scroll [UP](#ffmpeg-video-editing "Scroll to beginning of FFmpeg section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### cut video

```shell
# start at 0:00:01 and stop at 0:00:10
ffmpeg -v level+warning -stats -ss 1 -i INPUT.mp4 -to 10 -c copy OUTPUT.mp4

# start at 0:00:10 and stop at 0:00:20 (0:00:10 duration)
ffmpeg -v level+warning -stats -ss 10 -i INPUT.mp4 -t 10 -c copy OUTPUT.mp4

# caps output to be 0:00:30 max
ffmpeg -v level+warning -stats -i INPUT.mp4 -t 30 -c copy OUTPUT.mp4
```

timing from `-ss`, `-to`, and `-t` shift to the nearest frame and not at the exact timestamp when stream is copied (like here)

if exact time is needed the video needs to be re-encoded (`-c:v libx264` after or instead of `-c copy`) which obviously takes longer

when `-ss` is after `-i` it will decode and discard the video until the time is reached,
when it's before `-i` like here it will seek into the video without decoding it first (during the seek) so it will be faster.

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-ss` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dss%20position%20(input/output) "Documentation of `-ss position (input/output)`")
- [`-to` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dto%20position%20(input/output) "Documentation of `-to position (input/output)`")
- [`-t` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dt%20duration%20(input/output) "Documentation of `-t duration (input/output)`")
- [`-c` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dc%5B%3Astream_specifier%5D%20codec%20(input/output%2Cper%2Dstream) "Documentation of `-c[:stream_specifier] codec (input/output,per-stream)`")
  - [Stream specifiers documentation](https://ffmpeg.org/ffmpeg-all.html#Stream-specifiers "Documentation of stream specifiers for `-c`")

Scroll [UP](#ffmpeg-video-editing "Scroll to beginning of FFmpeg section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### loop video

```shell
# loop video infinitely but stop after 0:00:30
ffmpeg -v level+warning -stats -stream_loop -1 -i INPUT.mp4 -t 30 -c copy OUTPUT.mp4

# loop video to length of audio
ffmpeg -v level+warning -stats -stream_loop -1 -i INPUT.mp4 -i INPUT.mp3 -shortest -map 0:v -map 1:a OUTPUT.mp4

# loop audio to length of video
ffmpeg -v level+warning -stats -i INPUT.mp4 -stream_loop -1 -i INPUT.mp3 -shortest -map 0:v -map 1:a OUTPUT.mp4
```

if exact timing is needed, it is better to re-encode the video (`-c:v libx264` after or instead of `-c copy`)

> [!NOTE]
>
> Looping once means two playthroughs.

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-stream_loop` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstream_loop%20number%20(input) "Documentation of `-stream_loop number (input)`")
- [`-t` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dt%20duration%20(input/output) "Documentation of `-t duration (input/output)`")
- [`-c` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dc%5B%3Astream_specifier%5D%20codec%20(input/output%2Cper%2Dstream) "Documentation of `-c[:stream_specifier] codec (input/output,per-stream)`")
  - [Stream specifiers documentation](https://ffmpeg.org/ffmpeg-all.html#Stream-specifiers "Documentation of stream specifiers for `-c`")
- [`-shortest` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dshortest%20(output),-Finish%20encoding%20when%20the%20shortest%20output%20stream%20ends "Documentation of `-shortest (output)`")
- [`-map` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dmap%20%5B%2D%5Dinput_file_id%5B%3Astream_specifier%5D%5B%3F%5D%20%7C%20%5Blinklabel%5D%20(output) "Documentation of `-map [-]input_file_id[:stream_specifier][?] | [linklabel] (output)`")

Scroll [UP](#ffmpeg-video-editing "Scroll to beginning of FFmpeg section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### Reverse video and/or Audio

Warning: these filters require a lot of memory (buffer of the entire clip) so it's suggested to also use the trim filter as shown

```shell
# reverse video only (first 5sec)
ffmpeg -v level+warning -stats -i INPUT.mp4 -vf trim=end=5,reverse OUTPUT.mp4

# reverse audio only (first 5sec)
ffmpeg -v level+warning -stats -i INPUT.mp4 -af atrim=end=5,areverse OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [reverse filter documentation](https://ffmpeg.org/ffmpeg-all.html#reverse "Documentation of the reverse filter")
- [trim filter documentation](https://ffmpeg.org/ffmpeg-all.html#trim "Documentation of the trim filter")
- [areverse filter documentation](https://ffmpeg.org/ffmpeg-all.html#areverse "Documentation of the areverse filter")
- [atrim filter documentation](https://ffmpeg.org/ffmpeg-all.html#atrim "Documentation of the atrim filter")

Scroll [UP](#ffmpeg-video-editing "Scroll to beginning of FFmpeg section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### Concatenate multiple videos into one

```shell
# using filter complex and the concat filter (if video formats are not the same add `:unsafe` to the `concat` filter)
ffmpeg -v level+warning -stats -i INPUT_0.mp4 -i INPUT_1.mp4 -filter_complex "[0:v] [0:a] [1:v] [1:a] concat=n=2:v=1:a=1 [v1] [a1]" -map "[v1]" -map "[a1]" OUTPUT.mp4

# using a list file and demuxer
ffmpeg -v level+warning -stats -safe 0 -f concat -i VIDEO_LIST.txt -c copy OUTPUT.mp4
```

content of `VIDEO_LIST.txt` as follows

```text
file 'INPUT_0.mp4'
file 'INPUT_1.mp4'
```

> [!NOTE]
>
> all videos need to have the same resolution and fps for concat
>
> see [scale video](#scale-video) to scale all videos to the same resolution
> and [`-fps_mode`](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dfps_mode%5B%3Astream_specifier%5D%20parameter%20(output%2Cper%2Dstream) "Documentation of `-fps_mode[:stream_specifier] parameter` (output,per-stream)") `vfr`/`passthrough` to allow for variable frame rate

#### concat sections of videos

Cut clips and concat them (with re-encoding) as follows (video and audio are cut and combined separately).

```shell
# 00:00 to 00:02 video and audio of INPUT_0.mp4
# 00:04 to 00:08 video and audio of INPUT_0.mp4
# 00:01 to 00:05 video and audio of INPUT_1.mp4
# 00:06 to 00:08 video and audio of INPUT_1.mp4
ffmpeg -v level+warning -stats -i INPUT_0.mp4 -i INPUT_1.mp4 -filter_complex "[0:v]trim=0:2,setpts=PTS-STARTPTS[i0v0];[0:a]atrim=0:2,asetpts=PTS-STARTPTS[i0a0];[0:v]trim=4:8,setpts=PTS-STARTPTS[i0v1];[0:a]atrim=4:8,asetpts=PTS-STARTPTS[i0a1];[1:v]trim=1:5,setpts=PTS-STARTPTS[i1v0];[1:a]atrim=1:5,asetpts=PTS-STARTPTS[i1a0];[1:v]trim=6:8,setpts=PTS-STARTPTS[i1v1];[1:a]atrim=6:8,asetpts=PTS-STARTPTS[i1a1];[i0v0][i0a0][i0v1][i0a1][i1v0][i1a0][i1v1][i1a1]concat=n=4:v=1:a=1[cv][ca]" -map "[cv]" -map "[ca]" OUTPUT.mp4

# scale to WIDTH*HEIGHT with auto letter-/pilarbox and variable fps
ffmpeg -v level+warning -stats -i INPUT_0.mp4 -i INPUT_1.mp4 -filter_complex "[0:v]trim=0:2,setpts=PTS-STARTPTS,scale=WIDTH:HEIGHT:force_original_aspect_ratio=decrease,pad=WIDTH:HEIGHT:-1:-1,setsar=1[i0v0];[0:a]atrim=0:2,asetpts=PTS-STARTPTS[i0a0];[0:v]trim=4:8,setpts=PTS-STARTPTS,scale=WIDTH:HEIGHT:force_original_aspect_ratio=decrease,pad=WIDTH:HEIGHT:-1:-1,setsar=1[i0v1];[0:a]atrim=4:8,asetpts=PTS-STARTPTS[i0a1];[1:v]trim=1:5,setpts=PTS-STARTPTS,scale=WIDTH:HEIGHT:force_original_aspect_ratio=decrease,pad=WIDTH:HEIGHT:-1:-1,setsar=1[i1v0];[1:a]atrim=1:5,asetpts=PTS-STARTPTS[i1a0];[1:v]trim=6:8,setpts=PTS-STARTPTS,scale=WIDTH:HEIGHT:force_original_aspect_ratio=decrease,pad=WIDTH:HEIGHT:-1:-1,setsar=1[i1v1];[1:a]atrim=6:8,asetpts=PTS-STARTPTS[i1a1];[i0v0][i0a0][i0v1][i0a1][i1v0][i1a0][i1v1][i1a1]concat=n=4:v=1:a=1[cv][ca]" -map "[cv]" -fps_mode vfr -map "[ca]" OUTPUT.mp4
# for newer versions of ffmpeg, bicubic scaler is used, otherwise add `:flags=bicubic` to the scale filter to explicitly select it
# (if you want to only scale once and reuse the stream `[...]`, then it needs to be duplicated via `[...]split=N[..0][..1][..N]` filter to use in N places)
```

<details closed><summary>Click to show formatted first command</summary>

```text
ffmpeg
  -v level+warning
  -stats
  -i INPUT_0.mp4
  -i INPUT_1.mp4
  -filter_complex "
    [0:v] trim=0:2, setpts=PTS-STARTPTS[i0v0];
    [0:a]atrim=0:2,asetpts=PTS-STARTPTS[i0a0];

    [0:v] trim=4:8, setpts=PTS-STARTPTS[i0v1];
    [0:a]atrim=4:8,asetpts=PTS-STARTPTS[i0a1];

    [1:v] trim=1:5, setpts=PTS-STARTPTS[i1v0];
    [1:a]atrim=1:5,asetpts=PTS-STARTPTS[i1a0];

    [1:v] trim=6:8, setpts=PTS-STARTPTS[i1v1];
    [1:a]atrim=6:8,asetpts=PTS-STARTPTS[i1a1];

    [i0v0][i0a0]
    [i0v1][i0a1]
    [i1v0][i1a0]
    [i1v1][i1a1]
    concat=n=4:v=1:a=1
    [cv][ca]
  "
  -map "[cv]"
  -map "[ca]"
  OUTPUT.mp4
```

</details>

<details closed><summary>Click to show formatted second command</summary>

```text
ffmpeg
  -v level+warning
  -stats
  -i INPUT_0.mp4
  -i INPUT_1.mp4
  -filter_complex "
    [0:v]
      trim=0:2,
      setpts=PTS-STARTPTS,
      scale=WIDTH:HEIGHT:force_original_aspect_ratio=decrease,
      pad=WIDTH:HEIGHT:-1:-1,
      setsar=1
    [i0v0];
    [0:a]atrim=0:2,asetpts=PTS-STARTPTS[i0a0];

    [0:v] trim=4:8, setpts=PTS-STARTPTS,scale=WIDTH:HEIGHT:force_original_aspect_ratio=decrease,pad=WIDTH:HEIGHT:-1:-1,setsar=1[i0v1];
    [0:a]atrim=4:8,asetpts=PTS-STARTPTS[i0a1];

    [1:v] trim=1:5, setpts=PTS-STARTPTS,scale=WIDTH:HEIGHT:force_original_aspect_ratio=decrease,pad=WIDTH:HEIGHT:-1:-1,setsar=1[i1v0];
    [1:a]atrim=1:5,asetpts=PTS-STARTPTS[i1a0];

    [1:v] trim=6:8, setpts=PTS-STARTPTS,scale=WIDTH:HEIGHT:force_original_aspect_ratio=decrease,pad=WIDTH:HEIGHT:-1:-1,setsar=1[i1v1];
    [1:a]atrim=6:8,asetpts=PTS-STARTPTS[i1a1];

    [i0v0][i0a0]
    [i0v1][i0a1]
    [i1v0][i1a0]
    [i1v1][i1a1]
    concat=n=4:v=1:a=1
    [cv][ca]
  "
  -map "[cv]"
  -fps_mode vfr
  -map "[ca]"
  OUTPUT.mp4
```

</details>

---

> [!NOTE]
>
> if you want to use hardware acceleration like NVIDIA CUDA the `-hwaccel cuda -hwaccel_output_format cuda` is required to be in front of every `-i INPUT_N.mp4`

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-filter_complex` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dfilter_complex%20filtergraph%20(global) "Documentation of `-filter_complex filtergraph (global)`")
  - can also be read from a file via `-filter_complex_script` with `path/to/file.txt`, although this is not mentioned in the official documentation.
  - [trim multimedia filter](https://ffmpeg.org/ffmpeg-all.html#trim "Documentation of trim filter (for `-filter_complex`)")
  - [atrim multimedia filter](https://ffmpeg.org/ffmpeg-all.html#atrim "Documentation of atrim filter (for `-filter_complex`)")
  - [setpts/asetpts](https://ffmpeg.org/ffmpeg-all.html#setpts_002c-asetpts "Documentation of setpts and asetpts filter (for `-filter_complex`)")
  - [scale filter documentation](https://ffmpeg.org/ffmpeg-all.html#scale-1 "Documentation for the scale filter")
    - [scaler options](https://ffmpeg.org/ffmpeg-all.html#Scaler-Options "Documentation for scaler options")
    - also, see the [scale video](#scale-video "Scroll to this section") section
  - [pad filter documentation](https://ffmpeg.org/ffmpeg-all.html#pad-1 "Documentation for the pad filter")
  - [setsar filter documentation](https://ffmpeg.org/ffmpeg-all.html#setdar_002c-setsar "Documentation for the setsar filter")
  - [concat multimedia filter](https://ffmpeg.org/ffmpeg-all.html#concat-3 "Documentation of concat filter (for `-filter_complex`)")
- [`-map` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dmap%20%5B%2D%5Dinput_file_id%5B%3Astream_specifier%5D%5B%3F%5D%20%7C%20%5Blinklabel%5D%20(output) "Documentation of `-map [-]input_file_id[:stream_specifier][?] | [linklabel] (output)`")
- [concat demuxer documentation](https://ffmpeg.org/ffmpeg-all.html#concat "Documentation of concat demuxer") (concat via text file)
- [`-safe` option for concat demuxer](https://ffmpeg.org/ffmpeg-all.html#:~:text=safe,-if%20set%20to%201%2C%20reject%20unsafe%20file%20paths%20and%20directives "Documentation of `-safe` option for the concat demuxer")
- [`-c` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dc%5B%3Astream_specifier%5D%20codec%20(input/output%2Cper%2Dstream) "Documentation of `-c[:stream_specifier] codec (input/output,per-stream)`")
  - [Stream specifiers documentation](https://ffmpeg.org/ffmpeg-all.html#Stream-specifiers "Documentation of stream specifiers for `-c`")
- also, see the [compress video](#compress-video "Scroll to this section") section (specifically with GPU hardware acceleration / NVIDIA CUDA)

Scroll [UP](#ffmpeg-video-editing "Scroll to beginning of FFmpeg section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### Create/download video with m3u8 playlist

```shell
# this will whitelist urls (`-i`) for files available via file, http/s, tcp, tls, or crypto protocol (for this command, not permanent)
ffmpeg -v level+warning -stats -protocol_whitelist file,http,https,tcp,tls,crypto -i INPUT.m3u8 -c copy OUTPUT.mp4
ffmpeg -v level+warning -stats -protocol_whitelist file,http,https,tcp,tls,crypto -i https://example.com/INPUT.m3u8 -c copy OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-protocol_whitelist` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=protocol_whitelist%20list%20(input) "Documentation of `protocol_whitelist list (input)`")
- [`-c` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dc%5B%3Astream_specifier%5D%20codec%20(input/output%2Cper%2Dstream) "Documentation of `-c[:stream_specifier] codec (input/output,per-stream)`")
  - [Stream specifiers documentation](https://ffmpeg.org/ffmpeg-all.html#Stream-specifiers "Documentation of stream specifiers for `-c`")

Scroll [UP](#ffmpeg-video-editing "Scroll to beginning of FFmpeg section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### find silence parts in video

```shell
# finds sections min 240sec long and max -70db loud and writes them to LOG.txt
ffmpeg -v level+warning -stats -i INPUT.mp4 -af silencedetect=noise=-70dB:d=240 -f null - 2> LOG.txt
```

look for `[silencedetect @ *` lines in log file

```text
[silencedetect @ 0000000000******] silence_start: 01:00:02.500
[silencedetect @ 0000000000******] silence_end: 01:10:02.500 | silence_duration: 00:09:59.989
[silencedetect @ 000000000*******] silence_start: 02:00:02.500
[silencedetect @ 000000000*******] silence_end: 02:10:02.500 | silence_duration: 00:09:59.989
[...]
```

Scroll [UP](#ffmpeg-video-editing "Scroll to beginning of FFmpeg section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

## Libavfilter virtual input device (lavfi filtergraph)

Create new videos via [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device") and a [video source](https://ffmpeg.org/ffmpeg-all.html#Video-Sources "Documentation of different video sources").

- [sierpinski (pan)](#sierpinski-pan "Scroll to this section")
- [mandelbrot (zoom)](#mandelbrot-zoom "Scroll to this section")
- [(elementary) cellular automaton](#elementary-cellular-automaton "Scroll to this section")
- [life (Cellular automaton)](#life-cellular-automaton "Scroll to this section")
- [mptestsrc (animated test patterns)](#mptestsrc-animated-test-patterns "Scroll to this section")
- [empty (input)](#empty-input "Scroll to this section")
- [color (input)](#color-input "Scroll to this section")
- [smptebars (input)](#smptebars-input "Scroll to this section")
- [smptehdbars (input)](#smptehdbars-input "Scroll to this section")
- [testsrc (input)](#testsrc-input "Scroll to this section")
- [testsrc2 (input)](#testsrc2-input "Scroll to this section")
- [rgbtestsrc (input)](#rgbtestsrc-input "Scroll to this section")
- [yuvtestsrc (input)](#yuvtestsrc-input "Scroll to this section")
- [colorspectrum (input)](#colorspectrum-input "Scroll to this section")
- [colorchart (input)](#colorchart-input "Scroll to this section")
- [allrgb (input)](#allrgb-input "Scroll to this section")
- [allyuv (input)](#allyuv-input "Scroll to this section")

Honorable mention: [`ddagrab`](https://ffmpeg.org/ffmpeg-all.html#ddagrab "Documentation of ddgrab video source") which can be used to capture (Windows) desktop screen (/-cutout).

Scroll [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### sierpinski (pan)

Random pan of sierpinski carpet/triangle fractal.

defaults: `s=640x480`, `r=25` (fps), and `type=carpet`

```shell
ffmpeg -v level+warning -stats -f lavfi -i sierpinski OUTPUT.mp4
ffmpeg -v level+warning -stats -f lavfi -i sierpinski=type=triangle OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-f` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Df%20fmt%20(input/output) "Documentation of `-f fmt (input/output)`")
- [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device")
- [`sierpinski` video source](https://ffmpeg.org/ffmpeg-all.html#sierpinski "Documentation of sierpinski video source")

<blockquote id="lavfi_sierpinski.mp4">

<https://github.com/user-attachments/assets/f9e57cfa-cc97-4752-a7ab-0c36d0ac59e6>

```shell
ffmpeg -v level+warning -stats -f lavfi -i sierpinski -t 60 lavfi_sierpinski.mp4
```

</blockquote>

<blockquote id="lavfi_sierpinski_triangle.mp4">

<https://github.com/user-attachments/assets/0de5b690-902b-423c-8a7b-1ca714e5e2d4>

```shell
ffmpeg -v level+warning -stats -f lavfi -i sierpinski=type=triangle -t 60 lavfi_sierpinski_triangle.mp4
```

</blockquote>

Scroll [UP](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to beginning of Libavfilter virtual input device (lavfi filtergraph) section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### mandelbrot (zoom)

Continuous zoom into the Mandelbrot set.

> <https://en.wikipedia.org/wiki/Mandelbrot_set>

```shell
# Mandelbrot with the "inside" set to black (how it usually is displayed)
# default: 640*480 25fps and position:
# X = -0.743643887037158704752191506114774 (real axis)
# Y = -0.131825904205311970493132056385139 (imaginary axis, inverted to how it usually is displayed)
ffmpeg -v level+warning -stats -f lavfi -i mandelbrot=inner=black -t 60 OUTPUT.mp4
# limited to 60sec
# ! the frame generation gets slower the further in the zoom
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-f` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Df%20fmt%20(input/output) "Documentation of `-f fmt (input/output)`")
- [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device")
- [`mandelbrot` video source](https://ffmpeg.org/ffmpeg-all.html#mandelbrot "Documentation of mandelbrot video source")

<blockquote id="lavfi_mandelbrot_black_blur.mp4">

<https://github.com/user-attachments/assets/c40b7849-0a16-4d8e-a296-f70452a0ede8>

_speed up and blured to decrease file size_

```shell
ffmpeg -v level+warning -stats -f lavfi -i mandelbrot=inner=black:s=300x300:end_pts=75,avgblur=1 -t 43 lavfi_mandelbrot_black_blur.mp4
```

</blockquote>

> Also, see the same zoom (position, vertically flipped so it looks the same) in my (interactive) Mandelbrot viewer:
>
> <https://maz01001.github.io/AlmondBreadErkunder/#0:7189,null,-1.3,1.99:-0.7436438870371698,-0.7436438870371482,0.13182590420530219,0.13182590420532267>
>
> Source code and documentation (controls): <https://github.com/MAZ01001/AlmondBreadErkunder>

Scroll [UP](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to beginning of Libavfilter virtual input device (lavfi filtergraph) section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### (elementary) cellular automaton

"Waterfall" of a 1D cellular automaton.

> <https://en.wikipedia.org/wiki/Elementary_cellular_automaton>

```shell
# random seed, no custom pattern, rule 18, start with an empty screen
# fallback/defaults: s=320x508 r=24 rule=110
ffmpeg -v level+warning -stats -f lavfi -i cellauto=full=0 -t 60 OUTPUT.mp4
# limited to 60sec
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-f` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Df%20fmt%20(input/output) "Documentation of `-f fmt (input/output)`")
- [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device")
- [`cellauto` video source](https://ffmpeg.org/ffmpeg-all.html#cellauto "Documentation of cellauto video source")

<blockquote id="lavfi_cellauto_3.mp4">

<https://github.com/user-attachments/assets/a6d266bc-0375-423d-9b4c-22058f6c22c4>

```shell
ffmpeg -v level+warning -stats -f lavfi -i cellauto=full=0:seed=3 -t 60 lavfi_cellauto_3.mp4
```

</blockquote>

Scroll [UP](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to beginning of Libavfilter virtual input device (lavfi filtergraph) section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### life (Cellular automaton)

2D cellular automaton.

> <https://en.wikipedia.org/wiki/Cellular_automaton>

```shell
# Conway's Game of Life
# default: random grid 320*240 25fps rule S23/B3 (stay alive with 2/3 neighbors and born with 3 neighbors)
ffmpeg -v level+warning -stats -f lavfi -i life -t 60 OUTPUT.mp4
# limited to 60sec

# as above but with green color and a red afterglow of dying cells
ffmpeg -v level+warning -stats -f lavfi -i life=mold=25:life_color=\#00ff00:death_color=\#aa0000 -t 60 OUTPUT.mp4
# limited to 60sec
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-f` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Df%20fmt%20(input/output) "Documentation of `-f fmt (input/output)`")
- [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device")
- [`life` video source](https://ffmpeg.org/ffmpeg-all.html#life "Documentation of life video source")

<blockquote id="lavfi_life_3_200x200_scaled.mp4">

<https://github.com/user-attachments/assets/975fdfea-8dfb-42e1-8280-663830965290>

_smaller initial size and scaled up 4x (nearest neighbor) to reduce file size_

```shell
ffmpeg -v level+warning -stats -f lavfi -i life=mold=25:life_color=\#00ff00:death_color=\#aa0000:seed=3:s=200x200,scale=4*iw:-1:flags=neighbor -t 124 lavfi_life_3_200x200_scaled.mp4
```

- [`scale` filter documentation](https://ffmpeg.org/ffmpeg-all.html#scale "Documentation of `scale` filter")
  - [`flags` option (scaler options: `sws_flags`) scaling algorithm](https://ffmpeg.org/ffmpeg-all.html#sws_005fflags "Documentation of `sws_flags` scaling algorithms (`scale` filter uses these for its `flags` option)")

</blockquote>

Scroll [UP](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to beginning of Libavfilter virtual input device (lavfi filtergraph) section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### mptestsrc (animated test patterns)

These patterns are equal to those from the _MPlayer_ test filter.

default: `r=25` (fps) `t=all` (all 10 tests repeating) `m=30` (frames per test) `d=-1` (infinite duration)

tests: `dc_luma`, `dc_chroma`, `freq_luma`, `freq_chroma`, `amp_luma`, `amp_chroma`, `cbp`, `mv`, `ring1`, and `ring2`.

```shell
# 60sec, all tests (each 3sec)
ffmpeg -v level+warning -stats -f lavfi -i mptestsrc=m=3*25:d=60 OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-f` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Df%20fmt%20(input/output) "Documentation of `-f fmt (input/output)`")
- [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device")
- [`mptestsrc` video source](https://ffmpeg.org/ffmpeg-all.html#mptestsrc "Documentation of mptestsrc video source")

<blockquote id="lavfi_mptestsrc_all_3s.mp4">

<https://github.com/user-attachments/assets/3e6a4398-9321-4416-a7dc-a51e19e0a53e>

```shell
ffmpeg -v level+warning -stats -f lavfi -i mptestsrc=m=3*25:d=60 lavfi_mptestsrc_all_3s.mp4
```

</blockquote>

Scroll [UP](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to beginning of Libavfilter virtual input device (lavfi filtergraph) section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### empty (input)

default: `s=320x240`, `r=25` (fps), and `d=-1` (infinite duration)

```shell
# 1sec 1920*1080 60fps nothing (green)
ffmpeg -v level+warning -stats -f lavfi -i nullsrc=s=1920x1080:r=60:d=1 OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-f` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Df%20fmt%20(input/output) "Documentation of `-f fmt (input/output)`")
- [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device")
- [`nullsrc` video source](https://ffmpeg.org/ffmpeg-all.html#nullsrc "Documentation of nullsrc video source")

Scroll [UP](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to beginning of Libavfilter virtual input device (lavfi filtergraph) section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### color (input)

default: `s=320x240`, `r=25` (fps), and `d=-1` (infinite duration)

```shell
# 1sec solid color #ff9900
# default: 320*240 25 fps
ffmpeg -v level+warning -stats -f lavfi -i color=c=\#ff9900:d=1 OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-f` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Df%20fmt%20(input/output) "Documentation of `-f fmt (input/output)`")
- [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device")
- [`color` video source](https://ffmpeg.org/ffmpeg-all.html#color "Documentation of color video source")

Scroll [UP](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to beginning of Libavfilter virtual input device (lavfi filtergraph) section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### smptebars (input)

default: `s=320x240`, `r=25` (fps), and `d=-1` (infinite duration)

```shell
# color bars pattern, based on the SMPTE Engineering Guideline EG 1-1990
ffmpeg -v level+warning -stats -f lavfi -i smptebars OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-f` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Df%20fmt%20(input/output) "Documentation of `-f fmt (input/output)`")
- [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device")
- [`smptebars` video source](https://ffmpeg.org/ffmpeg-all.html#smptebars "Documentation of smptebars video source")

<blockquote>

<img id="lavfi_smptebars.png" height="300" src="./example/lavfi_smptebars.png" alt="lavfi_smptebars.png" title="ffmpeg -v level+warning -stats -f lavfi -i smptebars -frames 1 lavfi_smptebars.png">

```shell
ffmpeg -v level+warning -stats -f lavfi -i smptebars -frames 1 lavfi_smptebars.png
```

</blockquote>

Scroll [UP](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to beginning of Libavfilter virtual input device (lavfi filtergraph) section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### smptehdbars (input)

default: `s=320x240`, `r=25` (fps), and `d=-1` (infinite duration)

```shell
# color bars pattern, based on the SMPTE RP 219-2002
ffmpeg -v level+warning -stats -f lavfi -i smptehdbars OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-f` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Df%20fmt%20(input/output) "Documentation of `-f fmt (input/output)`")
- [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device")
- [`smptehdbars` video source](https://ffmpeg.org/ffmpeg-all.html#smptehdbars "Documentation of smptehdbars video source")

<blockquote>

<img id="lavfi_smptehdbars.png" height="300" src="./example/lavfi_smptehdbars.png" alt="lavfi_smptehdbars.png" title="ffmpeg -v level+warning -stats -f lavfi -i smptehdbars -frames 1 lavfi_smptehdbars.png">

```shell
ffmpeg -v level+warning -stats -f lavfi -i smptehdbars -frames 1 lavfi_smptehdbars.png
```

</blockquote>

Scroll [UP](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to beginning of Libavfilter virtual input device (lavfi filtergraph) section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### testsrc (input)

default: `s=320x240`, `r=25` (fps), `d=-1` (infinite duration), and `n=0` ($\displaystyle\textit{timestamp}\cdot10^n$)

_`n=0` shows timestamp in seconds and `n=3` shows timestamp in milliseconds_

```shell
# test pattern with animated gradient and timecode (seconds)
ffmpeg -v level+warning -stats -f lavfi -i testsrc OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-f` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Df%20fmt%20(input/output) "Documentation of `-f fmt (input/output)`")
- [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device")
- [`testsrc` video source](https://ffmpeg.org/ffmpeg-all.html#testsrc "Documentation of testsrc video source")

<blockquote id="lavfi_testsrc_n3.mp4">

<https://github.com/user-attachments/assets/4c9d23d4-72b5-46f8-bd80-8d01d5da380e>

```shell
ffmpeg -v level+warning -stats -f lavfi -i testsrc=n=3:d=60 lavfi_testsrc_n3.mp4
```

</blockquote>

Scroll [UP](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to beginning of Libavfilter virtual input device (lavfi filtergraph) section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### testsrc2 (input)

default: `s=320x240`, `r=25` (fps), `d=-1` (infinite duration), and `alpha=255` (opacity of background, 0 to 255)

_I couldn't see a difference with different `alpha` values, at least for `mp4`/`webm`/`webp`/`png`/`gif` file-formats_

```shell
# animated test pattern
ffmpeg -v level+warning -stats -f lavfi -i testsrc2 OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-f` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Df%20fmt%20(input/output) "Documentation of `-f fmt (input/output)`")
- [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device")
- [`testsrc2` video source](https://ffmpeg.org/ffmpeg-all.html#testsrc2 "Documentation of testsrc2 video source")

<blockquote id="lavfi_testsrc2.mp4">

<https://github.com/user-attachments/assets/be58cd1d-ec31-4e95-9823-21af5b1a8490>

```shell
ffmpeg -v level+warning -stats -f lavfi -i testsrc2=d=60 lavfi_testsrc2.mp4
```

</blockquote>

Scroll [UP](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to beginning of Libavfilter virtual input device (lavfi filtergraph) section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### rgbtestsrc (input)

default: `s=320x240`, `r=25` (fps), and `d=-1` (infinite duration)

```shell
# RGB test pattern (useful for detecting RGB vs BGR issues)
ffmpeg -v level+warning -stats -f lavfi -i rgbtestsrc OUTPUT.mp4
# there should be red, green, and blue stripes from top to bottom
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-f` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Df%20fmt%20(input/output) "Documentation of `-f fmt (input/output)`")
- [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device")
- [`rgbtestsrc` video source](https://ffmpeg.org/ffmpeg-all.html#rgbtestsrc "Documentation of rgbtestsrc video source")

<blockquote>

<img id="lavfi_rgbtestsrc.png" height="300" src="./example/lavfi_rgbtestsrc.png" alt="lavfi_rgbtestsrc.png" title="ffmpeg -v level+warning -stats -f lavfi -i rgbtestsrc -frames 1 lavfi_rgbtestsrc.png">

```shell
ffmpeg -v level+warning -stats -f lavfi -i rgbtestsrc -frames 1 lavfi_rgbtestsrc.png
```

</blockquote>

Scroll [UP](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to beginning of Libavfilter virtual input device (lavfi filtergraph) section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### yuvtestsrc (input)

default: `s=320x240`, `r=25` (fps), and `d=-1` (infinite duration)

```shell
# YUV test pattern
ffmpeg -v level+warning -stats -f lavfi -i yuvtestsrc OUTPUT.mp4
# Y (luminance, black/white)
# Cb (blue-difference chroma, yellow/grey/blue)
# Cr (red-difference chroma, turquoise/grey/red)
```

> <https://en.wikipedia.org/wiki/YCbCr>

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-f` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Df%20fmt%20(input/output) "Documentation of `-f fmt (input/output)`")
- [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device")
- [`yuvtestsrc` video source](https://ffmpeg.org/ffmpeg-all.html#yuvtestsrc "Documentation of yuvtestsrc video source")

<blockquote>

<img id="lavfi_yuvtestsrc.png" height="300" src="./example/lavfi_yuvtestsrc.png" alt="lavfi_yuvtestsrc.png" title="ffmpeg -v level+warning -stats -f lavfi -i yuvtestsrc -frames 1 lavfi_yuvtestsrc.png">

```shell
ffmpeg -v level+warning -stats -f lavfi -i yuvtestsrc -frames 1 lavfi_yuvtestsrc.png
```

</blockquote>

Scroll [UP](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to beginning of Libavfilter virtual input device (lavfi filtergraph) section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### colorspectrum (input)

default: `s=320x240`, `r=25` (fps), `d=-1` (infinite duration), and `type=black` (`black`/`white`/`all`)

```shell
ffmpeg -v level+warning -stats -f lavfi -i colorspectrum OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-f` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Df%20fmt%20(input/output) "Documentation of `-f fmt (input/output)`")
- [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device")
- [`colorspectrum` video source](https://ffmpeg.org/ffmpeg-all.html#colorspectrum "Documentation of colorspectrum video source")

<blockquote>

<img id="lavfi_colorspectrum_black.png" height="300" src="./example/lavfi_colorspectrum_black.png" alt="lavfi_colorspectrum_black.png" title="ffmpeg -v level+warning -stats -f lavfi -i colorspectrum -frames 1 lavfi_colorspectrum_black.png">

```shell
ffmpeg -v level+warning -stats -f lavfi -i colorspectrum -frames 1 lavfi_colorspectrum_black.png
```

</blockquote>

<blockquote>

<img id="lavfi_colorspectrum_white.png" height="300" src="./example/lavfi_colorspectrum_white.png" alt="lavfi_colorspectrum_white.png" title="ffmpeg -v level+warning -stats -f lavfi -i colorspectrum=type=white -frames 1 lavfi_colorspectrum_white.png">

```shell
ffmpeg -v level+warning -stats -f lavfi -i colorspectrum=type=white -frames 1 lavfi_colorspectrum_white.png
```

</blockquote>

<blockquote>

<img id="lavfi_colorspectrum_all.png" height="300" src="./example/lavfi_colorspectrum_all.png" alt="lavfi_colorspectrum_all.png" title="ffmpeg -v level+warning -stats -f lavfi -i colorspectrum=type=all -frames 1 lavfi_colorspectrum_all.png">

```shell
ffmpeg -v level+warning -stats -f lavfi -i colorspectrum=type=all -frames 1 lavfi_colorspectrum_all.png
```

</blockquote>

Scroll [UP](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to beginning of Libavfilter virtual input device (lavfi filtergraph) section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### colorchart (input)

default: `s=320x240`, `r=25` (fps), `d=-1` (infinite duration), `preset=reference` (`reference`/`skintones`), and `patch_size=64x64` (size of each tile)

```shell
# colors checker chart (6↔ * 4↕ = 24 tiles)
ffmpeg -v level+warning -stats -f lavfi -i colorchart OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-f` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Df%20fmt%20(input/output) "Documentation of `-f fmt (input/output)`")
- [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device")
- [`colorchart` video source](https://ffmpeg.org/ffmpeg-all.html#colorchart "Documentation of colorchart video source")

<blockquote>

<img id="lavfi_colorchart_reference_32x32.png" height="300" src="./example/lavfi_colorchart_reference_32x32.png" alt="lavfi_colorchart_reference_32x32.png" title="ffmpeg -v level+warning -stats -f lavfi -i colorchart=patch_size=32x32 -frames 1 lavfi_colorchart_reference_32x32.png">

```shell
ffmpeg -v level+warning -stats -f lavfi -i colorchart=patch_size=32x32 -frames 1 lavfi_colorchart_reference_32x32.png
```

</blockquote>

<blockquote>

<img id="lavfi_colorchart_skintones_32x32.png" height="300" src="./example/lavfi_colorchart_skintones_32x32.png" alt="lavfi_colorchart_skintones_32x32.png" title="ffmpeg -v level+warning -stats -f lavfi -i colorchart=preset=skintones:patch_size=32x32 -frames 1 lavfi_colorchart_skintones_32x32.png">

```shell
ffmpeg -v level+warning -stats -f lavfi -i colorchart=preset=skintones:patch_size=32x32 -frames 1 lavfi_colorchart_skintones_32x32.png
```

</blockquote>

Scroll [UP](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to beginning of Libavfilter virtual input device (lavfi filtergraph) section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### allrgb (input)

default: `r=25` (fps), and `d=-1` (infinite duration)

> [!IMPORTANT]
>
> fixed size of `4096x4096` (use `scale` filter to change size)

```shell
# all rgb colors (static 4096x4096 frames)
ffmpeg -v level+warning -stats -f lavfi -i allrgb OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-f` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Df%20fmt%20(input/output) "Documentation of `-f fmt (input/output)`")
- [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device")
- [`allrgb` video source](https://ffmpeg.org/ffmpeg-all.html#allrgb "Documentation of allrgb video source")

<blockquote>

<img id="lavfi_allrgb_halfed.png" height="300" src="./example/lavfi_allrgb_halfed.png" alt="lavfi_allrgb_halfed.png" title="ffmpeg -v level+warning -stats -f lavfi -i allrgb,scale=iw/2:-1 -frames 1 lavfi_allrgb_halfed.png">

_scaled down to half size (bicubic) to reduce file size_

```shell
ffmpeg -v level+warning -stats -f lavfi -i allrgb,scale=iw/2:-1 -frames 1 lavfi_allrgb_halfed.png
```

- [`scale` filter documentation](https://ffmpeg.org/ffmpeg-all.html#scale "Documentation of `scale` filter")
  - [`flags` option (scaler options: `sws_flags`) scaling algorithm](https://ffmpeg.org/ffmpeg-all.html#sws_005fflags "Documentation of `sws_flags` scaling algorithms (`scale` filter uses these for its `flags` option)")

</blockquote>

Scroll [UP](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to beginning of Libavfilter virtual input device (lavfi filtergraph) section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")

### allyuv (input)

default: `r=25` (fps), and `d=-1` (infinite duration)

> [!IMPORTANT]
>
> fixed size of `4096x4096` (use `scale` filter to change size)

```shell
# all yuv colors (static 4096x4096 frames)
ffmpeg -v level+warning -stats -f lavfi -i allyuv OUTPUT.mp4
```

- [`-v` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dloglevel%20%5Bflags%2B%5Dloglevel%20%7C%20%2Dv%20%5Bflags%2B%5Dloglevel "Documentation of `-loglevel [flags+]loglevel | -v [flags+]loglevel`")
- [`-stats` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Dstats%20(global) "Documentation of `-stats (global)`")
- [`-f` documentation](https://ffmpeg.org/ffmpeg-all.html#:~:text=%2Df%20fmt%20(input/output) "Documentation of `-f fmt (input/output)`")
- [`lavfi` virtual input device](https://ffmpeg.org/ffmpeg-all.html#lavfi "Documentation of lavfi virtual input device")
- [`allyuv` video source](https://ffmpeg.org/ffmpeg-all.html#allyuv "Documentation of allyuv video source")

<blockquote>

<img id="lavfi_allyuv_halfed.png" height="300" src="./example/lavfi_allyuv_halfed.png" alt="lavfi_allyuv_halfed.png" title="ffmpeg -v level+warning -stats -f lavfi -i allyuv,scale=iw/2:-1 -frames 1 lavfi_allyuv_halfed.png">

_scaled down to half size (bicubic) to reduce file size_

```shell
ffmpeg -v level+warning -stats -f lavfi -i allyuv,scale=iw/2:-1 -frames 1 lavfi_allyuv_halfed.png
```

- [`scale` filter documentation](https://ffmpeg.org/ffmpeg-all.html#scale "Documentation of `scale` filter")
  - [`flags` option (scaler options: `sws_flags`) scaling algorithm](https://ffmpeg.org/ffmpeg-all.html#sws_005fflags "Documentation of `sws_flags` scaling algorithms (`scale` filter uses these for its `flags` option)")

</blockquote>

Scroll [UP](#libavfilter-virtual-input-device-lavfi-filtergraph "Scroll to beginning of Libavfilter virtual input device (lavfi filtergraph) section")
    | [TOP](#some-useful-ffmpeg-commands "Scroll to top of document")
