# repetitions #
 
## Overview ##
 
100 points
 
Category: [General Skills](../)
 
Tags : `#base64`
 
## Description ##
 
Can you make sense of this file?
 
## Approach ##

The contents of the downloaded `enc_flag` file appears to be base64 encoded :

    $ cat enc_flag 
    VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
    RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
    MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
    VkpEVGxaYVdFMVhSbFZrTTBKVVZXMTRWMDVHV2toalJYUlhDazFyV25sVVZXaHpWakpHZEdWRlZs
    aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==

Running a base64 decode of the contents of `enc_flag` :

    $ base64 -d enc_flag
    VjFSQ2EyTXlSblJUV0dSVllrWmFWRmx0TlZOalJtUlhZVVU1YVZKVVZuaFdWekZoWVZkR2NrNVVX bUZTVmtwUVdWUkdibVZXVm5WUgpiSEJzWVRCd2VWVXhXbXBOUlRWSFdqTnNWZ3BYUjFKeVZGZHdW MlZzVWxaVmJFNW9UVVJDTlZaWE1XRlVkM0JUVW14V05GWkhjRXRXCk1rWnlUVWhzVjJGdGVFVlhi bTkzVDFWT2JsQlVNRXNLCg==

Still looking very much like a base64 string after decoding, only slightly shorter. Given the name of this challenge and assumption is made that the base64 encoding is repeated multiple times.

## Solution ##

During the CTF event I solved this challenge manually by chaining up the decodes in a manual fashion, which works when the number of repetitions is low (6 in this case) :

    $ base64 -d enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d
    picoCTF{........redacted........}

Where the actual flag value redacted for the purposes of this write up.

However for situations that may utilise higher orders of repetitions, a simply bash script to loop until solved, or `base64` decode fails would be a better solution.

