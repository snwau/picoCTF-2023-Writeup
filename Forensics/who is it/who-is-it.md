# who is it #

## Overview ##

100 points

Category: [Forensics](../)

Tags : `#email #whois`

## Description ##

Someone just sent you an email claiming to be Google's co-founder Larry Page but you suspect a scam.
Can you help us identify whose mail server the email actually originated from?
Download the email file here. Flag: picoCTF{FirstnameLastname}

## Approach ##

View the email and note `Received` from server :

    Received: from mail.onionmail.org (mail.onionmail.org. [173.249.33.206])
        by mx.google.com with ESMTPS id f16-20020a05600c4e9000b003a1947873d6si1882702wmq.224.2022.07.07.23.19.47
        for <francismanzi@gmail.com>
        (version=TLS1_3 cipher=TLS_AES_256_GCM_SHA384 bits=256/256);
        Thu, 07 Jul 2022 23:19:47 -0700 (PDT)
    Received-SPF: pass (google.com: domain of lpage@onionmail.org designates 173.249.33.206 as permitted sender) client-ip=173.249.33.206;
    Authentication-Results: mx.google.com;
       dkim=pass header.i=@onionmail.org header.s=jan2022 header.b=4sU2nk5Z;
       spf=pass (google.com: domain of lpage@onionmail.org designates 173.249.33.206 as permitted sender) smtp.mailfrom=lpage@onionmail.org;
       dmarc=pass (p=NONE sp=NONE dis=NONE) header.from=onionmail.org

`whois` on `mail.onionmail.org` or `onionmail.org` doesn't give any clues as the registration information is in the form of a company only, not in the form of `Firstname Lastname` as required by the flag.

However using the IP address provided as the `designated permitted sender` does :

    $ whois 173.249.33.206
    ... (snip) ...
    person:         Wilhelm Zwalina

    => picoCTF{........redacted........}

Actual flag value redacted for the purposes of this write up.    