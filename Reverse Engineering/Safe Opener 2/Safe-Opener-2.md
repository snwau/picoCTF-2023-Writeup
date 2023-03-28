# Safe Opener 2 #
 
## Overview ##
 
100 points
 
Category: [Reverse Engineering](../)
 
Tags : `#strings`
 
## Description ##
 
What can you do with this file?
I forgot the key to my safe but this file is supposed to help me with retrieving the lost key. Can you help me unlock my safe?
 
## Solution ##

Flag was found in the strings of compiled java class (actual flag value redacted for the purposes of the write-up) :

    $ strings -t x SafeOpener.class | grep picoCTF
      31d ,picoCTF{........redacted........}
