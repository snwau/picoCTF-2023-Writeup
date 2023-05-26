# Rules 2023 #
 
## Overview ##
 
100 points
 
Category: [General Skills](../)
 
Tags : 
 
## Description ##
 
Read the rules of the competition and get a little bonus!
[Rules](https://picoctf.org/competitions/2023-spring-rules.html).
 
## Approach ##

The rules were viewed in a web browser via the link provided. Viewing the page source and performing a text search for `"picoCTF{"`

## Solution ##

The flag was found in the alternate text for an image (actual flag value redacted for the purposes of this write up) :

    .... (snip) ....

    <h2 id="what-are-the-other-rules-and-terms-for-picoctf-2023">What are the other rules and terms for picoCTF 2023?</h2>

    <p>
        CMU may display one or more Competition leaderboards and/or scoreboards.
        These boards may be available to other Participants and/or the public,
        and may show the Team name, the country of residence and/or school
        identified by the Team leader, and/or the name of the School identified
        by the Team leader. 
        <img src="/img/rules_fl23.png" alt="picoCTF{........redacted........}"/>
    </p>

    .... (snip) ....    

