# PcapPoisoning #

## Overview ##

100 points

Category: [Forensics](../)
 
Tags : `#pcap`

## Description ##

How about some hide and seek heh?
Download this file and find the flag.

## Approach ##

Open the provided `trace.pcap` packet capture file in [Wireshark](https://www.wireshark.org) open and create a display filter to "Find" packet(s) constaining the "String" equal to "picoCTF", specifying "Packet bytes" to be inspected and using the "Narrow and Wide" character sets.

Found packet #507 @ Timestamp: 0.101836

TCP Payload :

    0000   45 00 00 52 00 01 00 00 40 06 c3 90 ac 10 00 02   E..R....@.......
    0010   0a fd 00 06 00 14 00 15 00 00 00 00 00 00 00 00   ................
    0020   50 02 20 00 50 18 00 00 70 69 63 6f 43 54 46 7b   P. .P...picoCTF{
    0030   50 36 34 50 5f 34 4e 34 4c 37 53 31 53 5f 53 55   ........redacted
    0040   35 35 33 35 35 46 55 4c 5f 34 64 37 32 64 66 63   ................
    0050   63 7d                                             .}

ASCII flag value redacted for the purposes of this write up.

