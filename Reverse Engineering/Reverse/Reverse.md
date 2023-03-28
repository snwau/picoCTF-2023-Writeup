# Reverse #
 
## Overview ##
 
100 points
 
Category: [Reverse Engineering](../)
 
Tags : `#strings`
 
## Description ##
 
Try reversing this file? Can ya?
I forgot the password to this file. Please find it for me?
 
## Solution ##
 
Flag was found in the strings of executable (actual flag value redacted for the purposes of the write-up) :

    $ strings -t x ret | grep pico
      2048 Password correct, please see flag: picoCTF{........redacted........}