Gradle License Report
=====================

A plugin for generating reports about the licenses of the dependencies for your Gradle project.

This plugin will resolve all your dependencies, and then scour them for anything that looks like relevant licensing information. The theory is
to automatically generate a report that you can hand to corporate IP lawyers in order to keep them busy.

This plugin eats its own dogfood: if you check out the project, you will get `build/reports/dependency-license/index.html` which can be 
retrieved to see an example.

Usage
-------

First, look up the most recent version [here](http://jcenter.bintray.com/com/smokejumperit/gradle/).

Then add this to your `build.gradle` file:
```
buildscript {
    repositories {
      jcenter()
    }   
    dependencies {
			// Replace $version with the current version
			classpath "com.smokejumperit.gradle.license:Gradle-License-Report:$version"
    }   
}

apply plugin:'license-report'
```

Then run `gradle dependencyLicenseReport` to generate your report in `build/reports/dependency-license`.

Included Details
-----------------

For each dependency, these details are included in the report, assuming that the information exists within the dependency archives:

* Module Name
* Module Group
* Module Version
* Manifest Name
* Manifest Description
* Manifest Project URL
* Manifest Vendor
* Manifest Version
* Manifest License(s) -- could be license names, URLs, and/or embedded files
* POM Name
* POM Description
* POM Project URL
* POM License(s) -- could be license names, URLs, and/or embedded files
** POM License(s) Distribution
** POM License(s) Comments
* POM Developer(s) -- name, e-mail, organization, role
* Packaged License Files, which is any file with the following base name:
** `license`
** `unlicense`
** `readme`
** `notice`
** `copying`
** `copying.lesser`

License
--------

This plugin is released under the Unlicense. See the `LICENSE` file for details.
