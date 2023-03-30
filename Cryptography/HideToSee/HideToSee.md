# HideToSee #
 
## Overview ##
 
100 points
 
Category: [Cryptography](../)
 
 
## Description ##
 
How about some hide and seek heh?
Look at this image here.
 
## Solution ##
 
The final command used to drop the flag during the event was :

$ steghide extract -sf atbash.jpg 
Enter passphrase: {press enter}
wrote extracted data to "encrypted.txt".
$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_xz00558y}

We can use CyberChef to decrypt the flag.
Atbash chiper
picoCTF{........redacted........}