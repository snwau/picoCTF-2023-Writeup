# Permissions #
 
## Overview ##
 
100 points
 
Category: [General Skills](../)
 
Tags : `#sudo`
 
## Description ##
 
Can you read files in the root file?
 
## Approach ##

Nothing of interest in the users home folder and we don't have permission to list the contents of `/root'` :

    $ ls /root
    ls: cannot open directory '/root': Permission denied

Suggesting we may need `sudo`, lets see what is available to us :

    $ picoplayer@challenge:~$ sudo -l
    [sudo] password for picoplayer: 
    Matching Defaults entries for picoplayer on challenge:
        env_reset, mail_badpass,
        secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

    User picoplayer may run the following commands on challenge:
        (ALL) /usr/bin/vi

## Solution ##

`vi` may be run as a superuser via `sudo`, so we'll run it using the following command to show us a directory listing of `/root` as we don't its contents as yet : 

    $ sudo vi /root

    " ============================================================================
    " Netrw Directory Listing                                        (netrw v165)
    "   /root
    "   Sorted by      name
    "   Sort sequence: [\/]$,\<core\%(\.\d\+\)\=\>,\.h$,\.c$,\.cpp$,\~\=\*$,*,\.o$,\.obj$,\.info$,\.swp$
    "   Quick Help: <F1>:help  -:go up dir  D:delete  R:rename  s:sort-by  x:special
    " ==============================================================================
    ../                                                                                                 
    ./
    .vim/
    .bashrc
    .flag.txt
    .profile
    .viminfo

Navigate to the `.flag.txt` file, hit enter to open and view the flag contents.
