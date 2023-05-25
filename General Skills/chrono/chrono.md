# chrono #
 
## Overview ##
 
100 points
 
Category: [General Skills](../)
 
Tags : `#crontab`
 
## Description ##
 
How to automate tasks to run at intervals on linux servers?
Additional details will be available after launching your challenge instance.
 
## Approach ##
 
Automating and scheduling of tasks is typically the role of cron jobs, managed by the cron table.

    $ crontab -l
    no crontab for picoplayer

    $ crontab -e
    no crontab for picoplayer - using an empty one
    update-alternatives: error: no alternatives for editor
    /usr/bin/sensible-editor: 25: editor: not found
    /usr/bin/sensible-editor: 28: nano: not found
    /usr/bin/sensible-editor: 31: nano-tiny: not found
    /usr/bin/sensible-editor: 34: vi: not found
    Couldn't find an editor!
    Set the $EDITOR environment variable to your desired editor.
    crontab: "/usr/bin/sensible-editor" exited with status 1

Ok, lets try viewing the cron table for root :

    picoplayer@challenge:~$ crontab -u root -l
    must be privileged to use -u

    picoplayer@challenge:~$ sudo -l
    [sudo] password for picoplayer: 
    Sorry, user picoplayer may not run sudo on challenge.

Still no luck.

## Solution ##
 
Lets try viewing the system-wide crontab :

    $ cat /etc/crontab
    # picoCTF{........redacted........}

Actual flag value redacted for the purposes of this write up.

## Notes ##

Whilst trying to work out the above solution during the event, I did happen to accidently view the flag visible in `/challenge/metadata.json`, which didn't seem like the intended solution and likely a permissions misconfiguration.