<a href='Hidden comment: 

= Important Note =

The tool does not come with any build JAR at the moment as it requires some of the Adobe ColdFusion server libraries which are not a part of this distribution. You must have a valid instance of CF server locally in order to be able to prepare a package suitable for you server version.
'></a>

# Building on your own #

## Project structure ##

cf-metrics currently consists of two modules:
  * cf-code-coverage - contains aspects and helper classes for preparing Adobe ColdFusion patch (JAR)
  * cf-client - a CFML client for presenting code coverage statistics

## Prerequisites ##

Sometimes it's best to build the cf-metrics JAR on your own using your local Java and cfusion.jar. In order to do so make sure you have Maven installed and follow those steps:

  1. edit the pom.xml of cf-code-coverage module
  1. set the **cfusion.version** property to a proper value (e.g. 11)
  1. set the "cfusion.jar.location" property (must point to a cfusion.jar location of your local ColdFusion distribution)
  1. set the "java.version" and specify Java version to use for compilation (e.g. 7)

Once the above is done build the maven project:

```

mvn clean package
```

## Deploying the JAR file ##

After the main artifact is created **cf-code-coverage-[version](version.md).jar** copy it to **{cfusion\_dir}/lib/updates** directory. Now you can restart your ColdFusion server. Easy, isn't it?

You should be able to see the following message in your server logs once the first CF template gets parsed.

![http://wiki.cf-metrics.googlecode.com/git/images/coverage-enabled-console.png](http://wiki.cf-metrics.googlecode.com/git/images/coverage-enabled-console.png)

Be aware that if you're using **Trusted cache** or **Save class files** then you have to navigate to your administration panel and make use of the "Clear Template Cache Now" button. This is required as the CFM templates got instrumented the moment they are transformed into JAVA.

> ![http://wiki.cf-metrics.googlecode.com/git/images/cf-admin-trusted-cache.png](http://wiki.cf-metrics.googlecode.com/git/images/cf-admin-trusted-cache.png)

# Deploying the JAR file (manually) #

Just download the cf{version}-code-coverage.jar which is suitable for your ColdFusion server version (if not present in the Downloads tab then you can generate it on your own - see the first section) and place it in your CF server installation directory under **/lib/updates** directory.

Restart the server and clear the trusted cache (if you're using one).
Cleaning the compiled templates cache can be also done manually by clearing **{cf\_server\_id}/WEB-INF/cfclasses** directory

# CF statistics viewer #

The tool comes with simple GUI written in ColdFusion which can be used to review code coverage statistics from the same server. The files are present in **{clone-dir}/cf-client** directory. You can copy them as any CFM template to a directory of our choice (of course visible to CF server).

The GUI makes uses of a Java Script library called gauge.js (http://bernii.github.io/gauge.js/) which is used to provide nice looking code coverage guages! :)