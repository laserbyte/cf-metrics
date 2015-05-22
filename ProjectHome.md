# Moved to GitHub #
Since now o cf-metrics are hosted on github under this URL: https://github.com/kacperus/cf-metrics

# ColdFusion 11 support #

  * cf-metrics have been modified a bit (aspectj weaving process) to make it compatible with the most recent Adobe **ColdFusion 11**.
  * recent changes are now present on the master branch
  * no direct JAR download is available for now
  * I'm planing to move my project to github in a near future

# Code Coverage for Adobe<sup>1</sup> ColdFusion #

If you're looking for an easy-to-use ColdFusion code-coverage tool for your CFM or CFC templates then you found it!

The aim of this project is to provide a set of tools which can be used to measure various statistics for your Cold Fusion application. In the initial version a code coverage possibilities were introduced.



# Features #

  * CFC components and CFM templates are covered
  * `<`cfscript`>` tag with it's content is supported
  * small footprint on the template execution
  * generated JAVA classes size is increased by 5% on average
  * no manual code instrumentation is required
  * easy to deploy and use (single JAR)

# How does this work? #

Code Coverage statistics are enabled by deploying a single JAR file into the **/lib/updates** directory of your Cold Fusion server as any other Adobe(R) patch file.

Once a file is requested and processed by a Cold Fusion engine Code Coverage statistics are recorded. They can be accessed later on via singleton instance of a TemplateCoverageTool (statistics collector class). Any desired visualization can be applied to it afterwards. A default ColdFusion statistics viewer (written in CFML) is provided as a side project.

# Example Visualization #

Example visualization of the gathered code coverage statistics is present below.

## General overview of code coverage client ##
> ![http://wiki.cf-metrics.googlecode.com/git/images/coverage-visualization-global.png](http://wiki.cf-metrics.googlecode.com/git/images/coverage-visualization-global.png)

## Details code coverage statistics for a particular file ##
> ![http://wiki.cf-metrics.googlecode.com/git/images/coverage-visualization-file.png](http://wiki.cf-metrics.googlecode.com/git/images/coverage-visualization-file.png)

## Code coverage of cfscript block ##
> ![http://wiki.cf-metrics.googlecode.com/git/images/coverage-visualization-cfscript.png](http://wiki.cf-metrics.googlecode.com/git/images/coverage-visualization-cfscript.png)

# Note #

<sup>1</sup> _Adobe stands for Adobe Systems Incorporated, a Delaware corporation, 345 Park Avenue, San Jose, California 95110, if subsection 10(a) of this Agreement applies; otherwise it means Adobe Systems Software Ireland Limited, Unit 3100, Lake Drive, City West Campus, Saggart D24, Dublin, Republic of Ireland, a company organized under the laws of Ireland and an affiliate and licensee of Adobe Systems Incorporated._

_Adobe and ColdFusion are either registered trademarks or trademarks of Adobe Systems Incorporated in the United States and/or other countries. All other trademarks are the property of their respective owners._