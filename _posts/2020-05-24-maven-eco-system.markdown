---
layout: post
title:  "Maven eco system"
date:   2020-03-03 09:55:00 +1000
categories: Geek
---

pom.xml
=========
heart of the configuration

###release plugin

To make a project production ready, we need to make a way for release. maven release plugin is created for this purpose.

In order to make a release, we need to have the source (i.e. version control repository), and destination (we choose nexus).

Here's the pom setup for release plugin. 

- For the source we use <scm> to define the repo url.

- For the destination, we use <distributionManagement> to define the nexus location.

- Then set the maven-release-plugin in the <plugin> section.

There are 2 step/goal in the release, `prepare` has a few checking and make the pom is ready, `perform` will check out the release tag, build and deploy the code to Nexus.

###parent and sub module

In most of the use case, more than one module live in the same project. We can use pom to manage the multi-module structure.

To sync the version accross the submodules with the parent we can setup like this.

In the parent, we can define the sub module like this

{% highlight java%}
<modules>
    <module>a</module>
    <module>b</module>
</modules>
{% endhighlight%}

In the submodule we just define the parent
{% highlight java%}
<parent>
    <groupId>.....</groupId>
    <artifactId>....</artifactId>
    <version>0.0.1</version>
</parent>
{% endhighlight%}

Then use the [maven relase plugin]() option to automate update the submodule version.
{% highlight java%}
mven release:prepare -DautoVersionSubmodules=true 
{% endhighlight%}

If the submodule need to pending on the other peers, we can use `${project.parent.version}` to get the parent version.

###sonar: code quality analyser

###dependency management


###loging

Maven Stage
===========

- test --- for unit test - plugin surefire

- verify --- for integration test - plugin failsafe

SCM Plugin
=============
connect to source code management e.g. SVN or Git repo


compared with Gradle
========








