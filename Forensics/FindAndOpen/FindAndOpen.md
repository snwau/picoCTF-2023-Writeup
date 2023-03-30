# FindAndOpen #

## Overview ##

200 points

Category: [Forensics](../)

Tags : `#pcap`

## Description ##

Someone might have hidden the password in the trace file.
Find the key to unlock `this file`. This `tracefile` might be good to analyze.

## Approach ##

Used [WireShark](https://www.wireshark.org) to open the provided `dump.pcap`, visually inspecting the packet payloads the following packet was found of interest, payload size stood out as unique in this capture also) :
  
    Packet #48 @ Timestamp: 24.240874
    Packet Type: Ethernet II

    Data = VGhpcyBpcyB0aGUgc2VjcmV0OiBwaWNvQ1RGe1IzNERJTkdfTE9LZF8=

Payload looked very reminiscent of a base64 encoded string :

    $ echo "VGhpcyBpcyB0aGUgc2VjcmV0OiBwaWNvQ1RGe1IzNERJTkdfTE9LZF8=" | base64 -d
    picoCTF{R34DING_LOKd_

Well thats a fragment of our flag, before continuing to search for additional payloads in the packet capture file I decided to try this as the password to unzip the supplied encrypted `flag.zip`, which yields a `flag` file containing the full flag (value redacted for the purposes of the write up) :

    picoCTF{........redacted........}

