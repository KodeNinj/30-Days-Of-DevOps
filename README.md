# MAVEN

## Introduction

One thing about DevOps is that it strive to automate the process involded in moving code from the developer's code editor to the production server so as to be visible to the users.
What happen after coding?

- The code will need to be built
- The built project will need to be tested
- Then it will be sent to different servers (production, DR, etc)

Maven is used for the building of the project after developers finish coding. It also carried out testing to be sure all the dependencies and other plugins needed to run the project is present and built with the code base.

### Lifecycle of MAVEN

- Clean Lifecycle: This removes previous build logs from the history.
- Default Lidecycle: This involves various actions. It is the default actions that is involved in compiling and deployment of the package to a remote repository for sharing with others and environments.

use this Pneumonics

- VCT - VISIT
- PID - PYD

```
- Validate: the project structure and verifies if all necessary information are available
This include images files, icon, plugins, etc
- Compile: the code after checking for syntax error
- Test: run unit test on the compiled project
- Package: into a distributed format called artifact (JAR, WAR, APK)
- Install: the package into a local repository (.m2)
- Deploy: the artifact into a remote repository.

NOTE: any command you run will always start from the Validate stage to that command you specify
```

- Site Lifecycle: generate project documentation and report

## HANDS-ON PROJECT

Pre-requisites

- AWS free tier account
