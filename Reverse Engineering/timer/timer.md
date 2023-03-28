# timer #
 
## Overview ##
 
100 points
 
Category: [Reverse Engineering](../)
 
Tags : `#android #apk #strings`
 
## Description ##
 
You will find the flag after analysing this apk.

## Solution ##

An android `.apk` file is a zip bundle, therefore unzipping and initially searching for the expected flag string locates the file to display the strings for.

    $ unzip timer.apk

    $ grep -rw picoCTF .
      grep: ./classes3.dex: binary file matches

    $ strings -t x classes3.dex | grep picoCTF
      160f *picoCTF{........redacted........}

Actual flag value redacted for the purposes of the write up.