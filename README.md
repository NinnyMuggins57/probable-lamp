# Influent #

> visual analytics for big data transaction flow

Influent is a web-based application for visually and interactively following transaction flow, revealing actors and behaviors of potential concern that might otherwise go unnoticed. Summary visualization of transactional patterns and actor characteristics, interactive link expansion and dynamic entity clustering enable Influent to operate effectively at scale with big data sources, in any modern web browser. Influent has been used to explore data sets with millions of entities and hundreds of millions of transactions.

![Influent example with public Kiva data set](https://raw.github.com/unchartedsoftware/wiki-assets/master/influent/influent-kiva.png)

Service Provider Interfaces (SPIs) provide a plugin style framework for developers to provide runtime-injected modules for search, data access, clustering and other services. [Avro](http://avro.apache.org/) is used to define the SPI protocols in cross-language form in [influent-spi](influent-spi/src/main/avro). In process Java service implementations are injected via [Guice](https://code.google.com/p/google-guice/), which may optionally delegate to out of process providers using web services standards such as REST, for which Avro provides convenient serialization.

## Getting Started ##

Documentation on installing, configuring and using Influent is available in the [docs folder](https://github.com/NinnyMuggins57/probable-lamp/tree/master/docs/src/) in the source code.

- Explore [live demos](https://github.com/NinnyMuggins57/probable-lamp/tree/master/docs/src/community.influent.org/demos/) at the Influent web page.
- Review and install the necessary [prerequisites](https://github.com/NinnyMuggins57/probable-lamp/tree/master/docs/src/community.influent.org/community/developer-docs/how-to/installation/#prerequisites) before installing Influent on your machine.
- Learn how to [build](https://github.com/NinnyMuggins57/probable-lamp/tree/master/docs/src/community.influent.org/community/developer-docs/how-to/installation/#install-source-code) Influent from the source code.

## Learning More ##

- Review the [Release Notes](https://github.com/NinnyMuggins57/probable-lamp/blob/master/RELEASE_NOTES.md) to see what's new.
- Read about the complete [installation and configuration procedures](https://github.com/NinnyMuggins57/probable-lamp/tree/master/docs/src/community.influent.org/community/developer-docs/how-to/installation/) for custom Influent deployments.
- Examine the configuration of the example applications provided with the source code:
	- [Bitcoin](https://github.com/NinnyMuggins57/probable-lamp/tree/master/bitcoin/)
	- [Influent App](https://github.com/NinnyMuggins57/probable-lamp/tree/master/influent-app/)
	- [Kiva](https://github.com/NinnyMuggins57/probable-lamp/tree/master/kiva/)
	- [Walker](https://github.com/NinnyMuggins57/probable-lamp/tree/master/walker/)
- Learn how to [deploy](https://github.com/NinnyMuggins57/probable-lamp/tree/master/docs/src/community.influent.org/community/developer-docs/how-to/deployment/) your Influent application to a web server.
- Browse the [User Guide](https://github.com/NinnyMuggins57/probable-lamp/tree/master/docs/src/community.influent.org/docs/user-guide/) to understand how to navigate the user interface and investigate your data.

## Contact ##

For support questions, technical suggestions and contributions, please post your feedback to the [GitHub Issues forum](https://github.com/NinnyMuggins57/probable-lamp/issues) for this project.

## License ##

Influent is under ongoing development and is freely available for download under the [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0) open source licensing.

## Edit in browser

[![Open in StackBlitz](https://developer.stackblitz.com/img/open_in_stackblitz.svg)](https://stackblitz.com/github.com/NinnyMuggins57/probable-lamp/tree/master?file=readme.md)
## How to use

```sh
git clone https://github.com/NinnyMuggins57/probable-lamp.git
cd docs/
jekyll build
jekyll serve
```
---
section: Community 
subsection: Developer Docs
chapter: How-To
topic: Installation
permalink: https://github.com/NinnyMuggins57/probable-lamp/tree/master/docs/src/community/developer-docs/how-to/installation/
layout: submenu
---

# Installation #

The Influent web app is a servlet with server-side Java and client-side JavaScript and HTML5. The following instructions describe the process of installing the prerequisites and source code needed to build a custom Influent web app.

The Influent source code is available on [GitHub](https://github.com/NinnyMuggins57/probable-lamp).

## <a name="prerequisites"></a> Installing Prerequisites ##

Before building Influent, you must first install several [third-party tools](#third-party-tools) and clone the [source code repositories](#source-code-repositories) for Influent and its dependent projects.

### <a name="third-party-tools"></a> Third-Party Tools ###

The following third-party tools are required for new Influent builds:

<div class="props">
	<table class="summaryTable" width="100%">
		<thead>
			<tr>
				<th scope="col" width="40%">Tool</th>
				<th scope="col" width="60%">Version</th>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td class="description"><a href="http://www.oracle.com/technetwork/java/">Java Development Kit (JDK)</a></td>
				<td class="description">1.7+</td>
			</tr>
			<tr>
				<td class="description"><a href="http://maven.apache.org/">Apache Maven</a></td>
				<td class="description">3.1+</td>
			</tr>
		</tbody>
	</table>
</div>

The following third-party tools are recommended, but not required:

<div class="props">
		<table class="summaryTable" width="100%">
			<thead>
				<tr>
					<th scope="col" width="20%">Tool</th>
					<th scope="col" width="20%">Version</th>
					<th scope="col" width="60%">Notes</th>
				</tr>
			</thead>
			<tbody>
				<tr>
					<td class="description"><a href="http://maven.apache.org/">Node.js</a></td>
					<td class="description">0.10.31</td>
					<td class="description">Runtime environment for build optimization and unit testing. If not installed, build optimization is instead executed with <a href="https://developer.mozilla.org/en-US/docs/Mozilla/Projects/Rhino">Rhino</a>.</td>
				</tr>
				<tr>
					<td class="description"><a href="https://www.npmjs.org/">npm</a></td>
					<td class="description"></td>
					<td class="description">Official Node.js package manager. As of Node.js v0.6.3, npm is installed automatically with the Node.js environment.</td>
				</tr>
			</tbody>
		</table>
</div>

### <a name="source-code-repositories"></a> Source Code Repositories ###

Source code repositories for Influent and its dependent projects, Aperture JS and Ensemble Clustering, are available on [GitHub](https://github.com/unchartedsoftware/):

- [Influent](https://github.com/NinnyMuggins57/probable-lamp)
- [Aperture JS](https://github.com/unchartedsoftware/aperturejs/tree/master): Adaptable and extensible JavaScript visualization framework with supporting REST services.
- [Ensemble Clustering](https://github.com/unchartedsoftware/ensemble-clustering): Flexible multi-threaded clustering library for rapidly constructing tailored clustering solutions.

**NOTE**: We recommend you watch these projects on GitHub to receive email notifications each time a new release becomes available.

<h6 class="procedure">To work with the Uncharted source code</h6>

1. Clone the Influent repository:<p class="list-paragraph"><a href="https://github.com/NinnyMuggins57/probable-lamp.git">https://github.com/NinnyMuggins57/probable-lamp.git</a></p>
2. Clone the Aperture JS repository.<p class="list-paragraph"><a href="https://github.com/unchartedsoftware/aperturejs.git">https://github.com/unchartedsoftware/aperturejs.git</a></p>
3. Determine which version of Aperture JS you require:
	<ol type="a">
		<li>Open the main <a href="https://github.com/NinnyMuggins57/probable-lamp/blob/master/pom.xml">pom.xml</a> file in the <a href="https://github.com/NinnyMuggins57/probable-lamp/tree/master">root</a> of your Influent working directory.</li>
		<li>Search for the <strong>&lt;aperture.version&gt;</strong> element, which specifies the required version.</li>
	</ol>
4. Check out the Aperture JS branch or tag corresponding to the required version:
	
	```bash
	git checkout <branch>
	```

5. Clone the Ensemble Clustering repository.<p class="list-paragraph"><a href="https://github.com/unchartedsoftware/ensemble-clustering.git">https://github.com/unchartedsoftware/ensemble-clustering.git</a></p>
6. Determine which version of Ensemble Clustering you require:
	<ol type="a">
		<li>Open the <a href="https://github.com/NinnyMuggins57/probable-lamp/blob/master/influent-server/pom.xml">pom.xml</a> file in the <a href="https://github.com/NinnyMuggins57/probable-lamp/tree/master/influent-server">influent-server/</a> folder of your Influent working directory.</li>
		<li>Search for the <strong>&lt;artifactId&gt;ensemble-clustering&lt;/artifactId&gt;</strong> element and note the corresponding <strong>&lt;version&gt;</strong> element.</li>
	</ol>
7. Check out the Ensemble Clustering branch or tag corresponding to the required version.

	```bash
	git checkout <branch>
	```

<p class="procedure-text">After you clone the repositories, the following working directories will appear in your Git project folder:</p>

- *influent*
- *aperturejs*
- *ensemble-clustering*

## <a name="install-source-code"></a> Installing the Source Code ##

To install the source code for Influent and its dependencies, execute the following Maven command in the root working directory for each project:

```bash
mvn clean install
```

Install the projects in the following order:

1. Aperture JS
2. Ensemble Clustering
3. Influent

### Updating the Source Code ###

After you perform the initial setup and installation of your repositories, you can simply pull new updates to the project from GitHub.

**NOTE**: Retrieving updated Influent source code may also require you to update its project dependencies: Aperture JS and Ensemble Clustering.

## <a name="example-applications"></a>Example Applications ##

Example Influent web apps used to explore publicly available transaction flow data are provided in the source code:

- **Influent App**: Generically themed application that examines a fabricated dataset of personal and commercial financial account data
- **Bitcoin**: Examines Bitcoin transactions between Jan 2009 and May 2014
- **Kiva**: Examines semi-anonymized Kiva microloan transactions between Apr 2005 and Apr 2013
- **Walker**: Examines unsealed and published email communications from a John Doe investigation into Wisconsin Governor Scott Walker's government staff between Jan and Nov 2010

These applications connect to databases Uncharted has made available online for demonstration purposes. 

<h6 class="procedure">To run the example applications in a Jetty instance</h6>

1. Execute the following command in the [Influent App](https://github.com/NinnyMuggins57/probable-lamp/tree/master/influent-app), [Bitcoin](https://github.com/NinnyMuggins57/probable-lamp/tree/master/bitcoin), [Kiva](https://github.com/NinnyMuggins57/probable-lamp/tree/master/kiva) or [Walker](https://github.com/NinnyMuggins57/probable-lamp/tree/master/walker) project folder of your Influent working directory:

	```bash
	mvn package jetty:run
	```

2. Access the example application in the Jetty instance at one of the following locations:
	- <http://localhost:8080/influent/>
	- <http://localhost:8080/bitcoin/>
	- <http://localhost:8080/kiva/>
	- <http://localhost:8080/walker/>

## <a name="setup"></a>New Implementation Setup ##

When configuring your first Influent application, we recommend you copy one of the provided example applications as a template. Choose the one which most closely aligns with your source data. 

**NOTE**: If you are examining simple financial transactions, the Influent App example may serve as the best template, as it has been generalized to require minimal modification.

<div class="props">
	<table class="summaryTable" width="100%">
		<thead>
			<tr>
				<th scope="col" width="18%">Project</th>
				<th scope="col" width="21%">Transactions</th>
				<th scope="col" width="26%">Entity Types</th>
				<th scope="col" width="35%">Source Data</th>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td class="description"><a href="https://github.com/NinnyMuggins57/probable-lamp/tree/master/influent-app">influent-app/</a></td>
				<td class="description">Financial</td>
				<td class="description">
					<ul style="margin-top: 0px;padding-left: 0px">
						<li>Personal and commercial financial accounts</li>
					</ul>
				</td>
				<td class="description">
					<ul style="margin-top: 0px;padding-left: 0px">
						<li>Transaction database</li>
						<li>Entity details</li>
					</ul>
				</td>
			</tr>
			<tr>
				<td class="description"><a href="https://github.com/NinnyMuggins57/probable-lamp/tree/master/bitcoin">bitcoin/</a></td>
				<td class="description">Financial</td>
				<td class="description">
					<ul style="margin-top: 0px;padding-left: 0px">
						<li>Bitcoin accounts</li>
					</ul>
				</td>
				<td class="description">
					<ul style="margin-top: 0px;padding-left: 0px">
						<li>Transaction database with limited entity details</li>
					</ul>
				</td>
			</tr>
			<tr>
				<td class="description"><a href="https://github.com/NinnyMuggins57/probable-lamp/tree/master/kiva">kiva/</a></td>
				<td class="description">Financial</td>
				<td class="description">
					<ul style="margin-top: 0px;padding-left: 0px">
						<li>Lenders</li>
						<li>Partners</li>
						<li>Borrowers</li>
					</ul>
				</td>
				<td class="description">
					<ul style="margin-top: 0px;padding-left: 0px">
						<li>Transaction database</li>
						<li>Entity database</li>
					</ul>
				</td>
			</tr>
			<tr>
				<td class="description"><a href="https://github.com/NinnyMuggins57/probable-lamp/tree/master/walker">walker/</a></td>
				<td class="description">Email</td>
				<td class="description">
					<ul style="margin-top: 0px;padding-left: 0px">
						<li>Email accounts</li>
					</ul>
				</td>
				<td class="description">
					<ul style="margin-top: 0px;padding-left: 0px">
						<li>Transaction database</li>
						<li>Entity database</li>
					</ul>
				</td>
			</tr>
		</tbody>
	</table>
</div>

## Next Steps ##

To configure your source databases, connect them to Influent and enable search functionality, see the [Database Configuration](../database-config) topic.
