# hideme #
 
## Overview ##
 
100 points
 
Category: [Forensics](../)
 
Tags : `#steganography #image #binwalk`
 
## Description ##
 
Every file gets a flag.
The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye here.

## Approach ##

Being new to the forensics category of challenges, I tried a number of things prior to finding the solution, including :

1. no obvious visible information obscured within the image file when viewed in an image viewer
2. selectively enabled/disabled RGB and alpha channels of the image as layers, nothing visible found
3. inspected the image file metadata with `exiftool`
4. searched the file with a hex editor ([ImHex](https://github.com/WerWolv/ImHex)) and using `strings`, there was no flag, however I did find references to a "secret" and "secret/flag.png", but nothing in the form of `picoCTF{flag}`.

## Solution ##

The `binwalk` utility identified a zip archive appended to the original flag image file :

    $ binwalk flag.png 

    DECIMAL       HEXADECIMAL     DESCRIPTION
    --------------------------------------------------------------------------------
    0             0x0             PNG image, 512 x 504, 8-bit/color RGBA, non-interlaced
    41            0x29            Zlib compressed data, compressed
    39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
    39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2997, uncompressed size: 3152, name: secret/flag.png
    43036         0xA81C          End of Zip archive, footer length: 22

The zip archive was extract using `binwalk` :

    $ binwalk -e flag.png

This yielded another `flag.png` within `hideme/_flag.png.extracted/secret/flag.png` which when viewed with an image editor and displayed the flag (actual flag value redacted for the purposes of this write up):

    picoCTF{........redacted........}