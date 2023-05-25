# MSB #
 
## Overview ##
 
200 points
 
Category: [Forensics](../)
 
Tags : `#image ##steganography`
 
## Description ##
 
This image passes LSB statistical analysis, but we can't help but think there must be something to the visual artifacts present in this image...
 
## Approach ##
 
The description and name of challenge suggests data may be hidden in the Most Significant Bit (MSB) of the RGB pixels values within the image.

Rather than writing a program to do this analysis, a quick google search found a python tool `sigBits.py` that can extract data from both LSB and MSB for analysis.

    $ wget https://artifacts.picoctf.net/c/306/Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png

    $ pip install Pillow
    $ wget https://raw.githubusercontent.com/Pulho/sigBits/master/sigBits.py

    $ python3 sigBits.py -t=msb Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png
   
## Solution ##
 
The generated output `outputSB.txt` was searched for `picoCTF` locating the flag (actual flag value redacted for the purposes of this write up) :

    picoCTF{........redacted........}

## Other Useful Information ##

Flag is located at offset `0x3CD6E` in the file, viewed from a Hex exitor such as [ImHex](https://imhex.werwolv.net), if you having trouble locating it within a text editor.

Alternatively, grep can be used and the output restricted to the matched string and using regex to add 50 characters after the "picoCTF" prefix

    $ cat outputSB.txt | grep -o -E "picoCTF.{0,50}"
    picoCTF{........redacted........}"Thou h