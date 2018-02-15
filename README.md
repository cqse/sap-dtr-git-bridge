SAP DTR Git Bridge
==================

Gradle scripts for mirroring SAP Design Time Repository (DTR) code changes into a Git repository.

Goal
----

* Gradle has been chosen as scripting language as we can provide all dependencies out of the box (JARs, Gradle) and a JVM should already be installed on the Teamscale server to run the scripts.
* For now the scripts are no "real" Gradle plugins, but regular Gradle files that can be applied from any Gradle project. The scripts might be converted into a Gradle plugin once a certain marturity level has been reached, for now ease of simple editing (also at customer site) is more important.

Usage
-----

* From the SAP Support Portal, download the DTR command line client
  * In the Download area, search for "DI CLIENTS"
  * Download the SCA archive that matches your NetWeaver Java installation
  * From the archive, extract `deploy archives/tc~di~cmd_tools~sda.sda`
  * From that archive, extract `di_cmd_tools.zip`
  * Extract that zip file to a location of your choice
* Open env.bat and adjust your JAVA_HOME as well as the location of the DI command line tools.
* Open build.gradle and add your connection details as well as a data directory and git root directory.
* call update-git.bat manually or from a scheduled script
