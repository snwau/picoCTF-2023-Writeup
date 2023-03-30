# rotation #

## Overview ##

100 points

Category: [Cryptography](../)

Tags : `#rot #substitution #cypher`

## Description ##

You will find the flag after decrypting this file
Download the encrypted flag.

## Approach ##

Given the name of this challenge, a rotation based substitution cypher is suspected.

Contents of the encrypted flag file :

    $ cat encrypted.txt 
    xqkwKBN{z0bib1wv_l3kzgxb3l_25l7k61j}

Encrypted text appears to follow the flag structure (i.e. `picoCTF{flag-value-here}`) without additional data obfuscating the flag.

Hence for a rotational substitution cypher we should be able to build up our translation table, using values we know from the flag structure :

    a b c d e f g h i j k l m n o p q r s t u v w x y z

      T                 c     F   i             o p

Translation table is case insensitive, now filling in the rest from the known letters and hence rotation point.

    a b c d e f g h i j k l m n o p q r s t u v w x y z

    s T u v w x y z a b c d e F g h i j k l m n o p q r

Now just substitute the encrypted text using this translation table :

        xqkwKBN{z0bib1wv_l3kzgxb3l_25l7k61j}
    =>
        picoCTF{                           }

Flag value left un-substituted for the purposes of this write up.

NOTE: if you really don't want to work this out by hand there are various [ROT websites](https://rot13.com) that you can cycle through the various rotations until the plain text is clear.
