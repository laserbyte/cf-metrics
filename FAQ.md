# FAQ #



## How to use it? ##
> The best would be to navigate to the installation page in the WIKI. It is explained there step by step how to use Code Coverage for ColdFusion.

<a href='Hidden comment: 
== Why there is no "Downloads" tab? ==
Downloads tab have been disabled at the moment because currently there is nothing to download :) This doesn"t mean the project is not complete. The trick is you have to own your own copy of Adobe ColdFusion cfusion.jar file (which is not a part of this project) to prepare a patch which offers Code Coverage features.
'></a>

## What is the Aspecj used for? ##
> Aspectj are used to modify some of the cfusion.jar classes and inject additional code into them.

## Class not found exception: org.aspectj.lang.NoAspectBoundException ##
> The tool relies on AspectJ and requires the aspectjrt.jar to be present on the CF server class path. It's not included in the patch jar file and has to be provided separately but is a dependency of maven project.

## Is it safe to use it on production environments? ##
> Well, it shouldn't cause any troubles but it's not recommended. There is not guarantee it won't brake something as my intention was to use it only on staging and QC environments for testing purposes only.

## Plans for the future? ##
> I would love to create an Eclipse plugin which would show live code coverage of your local or remote server. Any contribution is more than welcome here! :)