# useless #
 
## Overview ##
 
100 points
 
Category: [General Skills](../)
 
Tags : `#man`
 
## Description ##
 
There's an interesting script in the user's home directory
The work computer is running SSH. We've been given a script which performs some basic calculations, explore the script and find a flag.
 
## Solution ##
 
The home folder contains a `useless` bash shell script that performed arithmetic calculations. After playing around with the script for some time I noticed the reference to the `man` keyword in the challenge description tags.

    $ man useless
    picoCTF{........redacted........}

Actual flag value redacted for the purposes of this write up.
