# Roadkill - Morphis Tech Developer Branch

These are instructions for Morphis developers. Please refer to [master](https://github.com/daniel-cordeiro/roadkill/tree/master) for a rundown on the Roadkill project.

### Pre-requisites

To setup Roadkill on a developer machine, you will need:

* Visual Studio
* Typescript installed - http://www.typescriptlang.org
* SQL Server Express 2012 or better, although you can configure Roadkill to work with SQL Server CE or SQLite if you prefer.
  * **Note: *If you don't want to add core functionality that interacts with the default database schema, you can use the demo Postgres database (Roadkill) running at AWS-RDS.***

### Fresh install (morphis-tech environment)


Follow these instructions in order to deploy and run the project on your machine.
* Open the solution (Roadkill.sln) on Visual Studio.
* Set up *Roadkill&#46;Web* as the Startup Project.
* Build the solution. If everything goes as expected, both *Roadkill&#46;Web* and *Roadkill&#46;Core* should build successfully.
* Run/Debug over IIS using your preferred browser.

### Build scripts (can be used on generation scripts)

There are 4 build scripts that automate the builds:

* build.ps1 - runs msbuild with the solution file. Same as building on Visual Studio.
* devbuild.ps1 - builds and copies all files required for a dev build, zips the files and then pushes the zip file to the 'RoadkillBuilds' repository on Bitbucket (https://bitbucket.org/yetanotherchris/roadkillbuilds).
* releasebuild.ps1 - The same as devbuild.ps1 but uses the `release` build configuration and only produces a zip file.
* mono.releasebuild.ps1 - Uses the the `mono` build configuration. Use this on Linux.
