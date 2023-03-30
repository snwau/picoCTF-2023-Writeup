# ReadMyCert #

## Overview ##

100 points

Category: [Cryptography](../)

Tags : `#certificate #base64`

## Description ##

How about we take you on an adventure on exploring certificate signing requests
Take a look at this CSR file.

## Approach ##

Dumping the contents of the `readmycert.cer` file yields :

    -----BEGIN CERTIFICATE REQUEST-----
    MIICpzCCAY8CAQAwPDEmMCQGA1UEAwwdcGljb0NURntyZWFkX215Y2VydF9hNzE2
    M2JlOH0xEjAQBgNVBCkMCWN0ZlBsYXllcjCCASIwDQYJKoZIhvcNAQEBBQADggEP
    ADCCAQoCggEBAL6KBBqiFmUHDwT3NtVw+Ozveo9uAZ+c47X5n+MEsWPowsNIz9fG
    kpLf9rgu9kR4ZR1H5IEddOGEsTA9qRUc1mwBuZeld5o9ltDU+6YzCKANDnwS61sB
    w4FV54LTy33T1+1bc11o++3LM34pFCGWI3lwoj8GWDRJdxvvp5Iwh5kz4ki6Mwp/
    HAKyyG9i9KMOXAm/Zw0FkL1UZppHa00cbdCieen7lZgeVpFlIs3uo8tL6fGmpYww
    Ard6ZFzL1zCwgZukSHsul20gi9Ba4Uz3R4f6zA/PL0S7haAif96yyi/REREKUZGt
    76Gt8zv2xVAqhZYYpFqOmv1ycRmZSyF8GWkCAwEAAaAmMCQGCSqGSIb3DQEJDjEX
    MBUwEwYDVR0lBAwwCgYIKwYBBQUHAwIwDQYJKoZIhvcNAQELBQADggEBAI4mtS0h
    2HQseRJfnySGJdsnquMyLSV1EdvAfb2qTosXuQH0vunk5NbnR9yjXKej0I2Uu6DW
    f9UehV+QsgW1tmZKpjGXj602nESDBVwiyNw84AXaW74+vH1lVKu9YFf08GI40Fee
    jYYjQLz6DatXL0Qsuyjjo/MF1W1z/N7ErLvox7tj+dIOfEs14LYx61JrwwcAw8Ak
    1lo4gwusg/+aEpAhDcw62Bjh2iGfwydHV7vh04vWBzPoSz5xyrNG+w8kALKKRUTh
    Z9wKzilfeMGpobC7at6ys5cMdrC3ePVxn0XWTQEWfjQwtr+UtOoOWlP8eJEstWQU
    qbdZveR4nsgbnkU=
    -----END CERTIFICATE REQUEST-----

Looks base64 encoded, running through an online [base64 decoder](https://www.base64decode.org), the flag is found in amongst the decoded output :

    picoCTF{........redacted........}

Flag value redacted for the purposes of this write up.
