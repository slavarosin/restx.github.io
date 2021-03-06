---
filename: ide-eclipse.md
title: Eclipse Setup
layout: docs
---
# Project setup in Eclipse

<div class="note">
	<p>Instructions are provided here for each of supported build tools: Ivy and Maven.</p>
	<p>If you don't want to use any of these, follow the instructions for Ivy, they include more manual steps.</p>
</div>

<div class="tab-head">
<a href="#ivy"><h2>Ivy</h2></a>
</div>

To setup your RESTX project inside Eclipse with Ivy support you will need to:

- install IvyDE
- create and configure the project
- enable and configure annotation processing

### Install IvyDE

First you need to install the [IvyDE](http://ant.apache.org/ivy/ivyde/) plugin in eclipse if you don't already have it.

To do so, use the **Help -> Install new software** action, add the IvyDE update site `http://www.apache.org/dist/ant/ivyde/updatesite` and install the IvyDE plugin.

![Install IvyDE](/images/docs/eclipse-install-ivyde-add-repo.png)
![Install IvyDE](/images/docs/eclipse-install-ivyde.png)

### Create and configure the project

First use **New -> Java Project** action to create a new Java project, and select the location where you have created the project.

![New RESTX project in eclipse](/images/docs/eclipse-new-project.png)

Then configure the source folders. Eclipse should detect `src/main/java` and `src/test/java`, you will need to add `src/main/resources` and `src/test/resources` manually:

![Configure RESTX project source folders in Eclipse](/images/docs/eclipse-new-project-sources.png)

Now open the Libraries tab and add an IvyDE Managed Dependencies library, selecting `module.ivy` as Ivy file:

![Configure RESTX project libraries in Eclipse](/images/docs/eclipse-new-project-libraries-1.png)
![Add IvyDE Managed Dependencies for RESTX](/images/docs/eclipse-new-project-add-library.png)
![Options for IvyDE Managed Dependencies for RESTX](/images/docs/eclipse-new-project-add-library-options.png)
![Configure RESTX project libraries in Eclipse](/images/docs/eclipse-new-project-libraries-2.png)

You're now ready to hit the finish button!

### Enable and configure annotation processing

The last step is to enable and configure annotation processing. Open project properties, and the go to the Annotation processing entry. Enable annotation processing and select the detination folder (we recommend using maven conventions, `target/generated-sources/annotations`).

![Enable annotation processing for RESTX in Eclipse](/images/docs/eclipse-annotation-processing-settings.png)

Then you need to configure the factory path for eclipse to discover the annotation processors. Eclipse does not allow to use the classpath for that, but RESTX provides a package containing everything needed for annotation processing in a single jar.

You can download it here:
http://repo1.maven.org/maven2/io/restx/restx-annotation-processors-package/{{ site.restx-version }}/restx-annotation-processors-package-{{ site.restx-version }}.jar

Then add it to the annotation processing factory path:

![Annotation processing factory path for RESTX in Eclipse](/images/docs/eclipse-annotation-processing-settings-factory-path.png)

Your project is now setup, you're ready to start coding!

If this is your first time with RESTX and followed this doc with the generated app, you probably want to [try it out now!](try-generated-app.html)

<div class="go-next">
	<ul>
		<li><a href="try-generated-app.html"><i class="icon-rocket"> </i> Try the generated app</a></li>
		<li><a href="generated-app-explained.html"><i class="icon-cogs"> </i> Understand generated app</a></li>
		<li><a href="getting-started.html"><i class="icon-play"> </i> Getting started</a></li>
		<li><a href="/community/"><i class="icon-beer"> </i> Community</a></li>
		<li><a href="/docs/"><i class="icon-book"> </i> Documentation</a></li>
	</ul>
</div>

<div class="tab-head">
<a href="#maven"><h2>Maven</h2></a>
</div>

If you have chosen to use Maven and [have generated a pom](getting-started.html) for the project (or hand written one following the [provided instructions](manual-app-bootstrap.html)), then you can use Eclipse Maven support (through the m2e plugin) to import the project.

What you will need to do:

- setup maven annotation processing in preferences
- import the project as a regular maven project

### setup maven annotation processing in preferences

Open eclipse preferences, go to **Maven -> Annotation processing** and select `Automatically configure JDT APT`:

![setup maven annotation processing in preferences](/images/docs/eclipse-maven-preferences-apt.png)

### import the project as a regular maven project

Use the **File -> Import** menu and choose `Existing Maven Projects`:

![import existing maven project into eclipse](/images/docs/eclipse-import-maven-project.png)

If this is your first time with RESTX and followed this doc with the generated app, you probably want to [try it out now!](try-generated-app.html)

<div class="go-next">
	<ul>
		<li><a href="try-generated-app.html"><i class="icon-rocket"> </i> Try the generated app</a></li>
		<li><a href="generated-app-explained.html"><i class="icon-cogs"> </i> Understand generated app</a></li>
		<li><a href="getting-started.html"><i class="icon-play"> </i> Getting started</a></li>
		<li><a href="/community/"><i class="icon-beer"> </i> Community</a></li>
		<li><a href="/docs/"><i class="icon-book"> </i> Documentation</a></li>
	</ul>
</div>
