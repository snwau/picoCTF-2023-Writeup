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
    $ get https://raw.githubusercontent.com/Pulho/sigBits/master/sigBits.py

    $ python3 sigBits.py -t=msb Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png 
    $ subl outputSB.txt
   
## Solution ##
 
The generated output `outputSB.txt` was searched for `picoCTF` locating the flag (actual flag value redacted for the purposes of this write up) :

    picoCTF{........redacted........}