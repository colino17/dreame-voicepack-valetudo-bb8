# BB8 Voicepack for Dreame Robots with Valetudo

## Installation (BB8)

    In Valetudo go to "Robot Settings" -> "Misc Settings"
    Enter the following information in the "Voice packs" section:
        URL: https://github.com/colino17/dreame-voicepack-valetudo-bb8/raw/main/voicebb8.tar.gz
        Language Code: BB8
        Hash: 86a1e0a848ecb6b6a7e1d14b65a29085
    Click "Set Voice Pack"

## Installation (R2D2)

    In Valetudo go to "Robot Settings" -> "Misc Settings"
    Enter the following information in the "Voice packs" section:
        URL: https://github.com/colino17/dreame-voicepack-valetudo-bb8/raw/main/voicer2d2.tar.gz
        Language Code: R2D2
        Hash: ee7b4b4acfc153bc83d97ee02866f09f
    Click "Set Voice Pack"

## Notes on File Formats

These particular robots seem very sensitive to file formats, bitrates, etc. After banging my head against a wall for quite some time wondering why some of my sounds worked fine, but others didn't play at all, I stumbled across [this article](https://blog.davidv.dev/posts/spicing-up-a-robot-vacuum/) which detailed the specific ffmpeg encoding settings required.

Here's a small shell script for bulk converting audio files to the right format. Remember to create an "out" subfolder and change "wav" in the first line to whatever the extension of the source files is.

```bash
#!/bin/sh

for i in *.wav
do
  ffmpeg -i "$i" -ac 1 -ar 16000 "out/${i%.*}.ogg"
done
```
