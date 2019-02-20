# SAP DTR Git Bridge [![Build Status](https://travis-ci.org/cqse/sap-dtr-git-bridge.svg?branch=master)](https://travis-ci.org/cqse/sap-dtr-git-bridge)

Gradle scripts for mirroring SAP Design Time Repository (DTR) code changes into a Git repository.

## Goal

* Gradle has been chosen as scripting language as we can provide all dependencies out of the box (JARs, Gradle) and a JVM should already be installed on the Teamscale server to run the scripts.
* For now the scripts are no "real" Gradle plugins, but regular Gradle files that can be applied from any Gradle project. The scripts might be converted into a Gradle plugin once a certain marturity level has been reached, for now ease of simple editing (also at customer site) is more important.

## Required Privileges in DTR

The configured user requires the _export_ privilege on the resource within the DTR (i.e. `<dtr.url>/<dtr.remoteRootDir>`).

## Usage

* From the SAP Support Portal, download the DTR command line client
  * In the Download area, search for "DI CLIENTS"
  * Download the SCA archive that matches your NetWeaver Java installation
  * From the archive, extract `deploy archives/tc~di~cmd_tools~sda.sda`
  * From that archive, extract `di_cmd_tools.zip`
  * Extract that zip file to a location of your choice
* Open `build.gradle` and add your connection details as well as a data directory, git root directory and the location of the DI command line tools.


### Windows
* call `gradlew.bat updateGit` manually or from a scheduled script

### Linux
* Execute `chmod +x file` for `gradlew` and `di_cmd/dtr/dtr.sh`.
* Open the di_cmd/dtr/dtr.sh and replace `#!/bin/sh` with ` #!/usr/bin/env bash` in the first line.
* Save the file with unix line ending (has windows line ending by default). E.g. Gedit -> Save As -> Line Ending -> Unix/Linux
* call `./gradlew updateGit` manually or from a scheduled script