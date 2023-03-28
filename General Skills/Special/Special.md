# Special #
 
## Overview ##
 
300 points
 
Category: [General Skills](../)
 
Tags : `#bash`
 
## Description ##
 
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)
 
## Approach ##
 
This took *a lot* of experimenting with bash shell syntax that I was familiar, throwing everything at the wall until I stumbled on the use of `((cat))` whilst trying to concatenate potential flag files in the working folder. This command would not emit the typical error and would await for further input on standard input, as if `cat` command was being executed without arguments.

Knowing this, and assuming `cat` could be replaced by any command, the next test was to use `((ls))` to start gathering information about what is in the current working folder that may be accessible.

`((ls))` showed a single entry `blargh`.

I then spent a quite a while trying to interact with `blargh` and the method of command execution I had found. What I quickly realised though was the `((<command>))` mechanism did not facilitate the use of arguments, for example attempts to `cat blargh` or `ls -al` failed, they were not being parsed properly by the "Special (TM)" interpretor.

There had to be a method of getting additional data into commands, which is when I started experimenting with input redirection. Finding the following command syntax was doing as I expected:

    ((cat)) < blargh

This returned an error indicating `blargh` was actually a directory and not a file, therefore having a guess at its possible contents led to the final solution.
 
## Solution ##
 
The final command used to drop the flag during the event was :

    Special$ ((cat)) < blargh/flag.txt
    ((cat)) < blargh/flag.txt 
    picoCTF{........redacted........}

Actual flag value redacted for the purposes of this write up.