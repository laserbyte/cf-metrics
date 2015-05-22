# Introduction #

If you came across this page then probably you're a ColdFusion developer who seeks for a code coverage tool for your CFM templates or CFC components? Am I right?

If that's the case then you're in the right place!

# History #

I was in the same place, looking for a CF code coverage tool couple months ago and the only tool I found was "[Rancho](http://rancho.riaforge.org/)" created by Kunal Saini.

Unfortunately despite first positive impression I found it problematic to use especially for the large code base I was dealing with (over 3k templates). Additionally the tool isn't compatible with CF8 my company was using so I had to modify Rancho's code (written in CF9) in order to make it work for me. It was not what I wanted...

My managed asked me if there aren't any other tools or possibilities we could try. Since I hadn't found any I started my own project and finally after many hours spent learning my enemy (CF engine) I finally got a tool which does what I need.

# Long story short #

My starting point was simple: CF engine knows which lines are currently executed so maybe it can expose / share that knowledge with me :) E.g. when exception is thrown exact line number and column are provided in CF stack trace for each template. This is where I started my journey...

This turned out to be partially a dead-end but I didn't gave up. By knowing how CFM templates are translated into JAVA classes I begun to analyze CF engine mechanisms: how the page is assembled, how a JAVA byte-code is generated with a help of [BCEL](http://commons.apache.org/proper/commons-bcel) and then managed by templates managers and finally stored in a cache.

By knowing the above and with a help of AspectJ I was able to inject my custom code into the original CF engine classes. Having this done I was able to generate "modified" byte-code during CFM to JAVA translation.

If you're interested in knowing more then please refer to the [Mechanism](Mechanism.md) page which tries to explain in more details how does this work. This is for the curious ones :)

# Usage #

I've tried to make the tool as easy to use as possible and therefore decided to deliver it in a form of typical CF patch JAR. All that needs to be done is to copy it into lib/updates directory of your CF engine. Restart it and clear trusted cache via admin console (or manually). That's it!