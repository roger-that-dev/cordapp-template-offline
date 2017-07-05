![Corda](https://www.corda.net/wp-content/uploads/2016/11/fg005_corda_b.png)

# CorDapp Template: Offline Version

Versions supported: `M12.1`

This is a version of the CorDapp template which has been adapted for use on networks with limited
connectivity to the outside World!

#### Pre-requisites:

* Oracle JDK 1.8u131
* IntelliJ IDEA CE (Minimum version 2017.1 at the time of writing)
* git

#### Changes made:

* Adapted `build.gradle` file to look for all the Corda dependencies in the `/lib/dependencies` folder
* Adapted `gradle-wrapper.properties` file to look for `gradle-3.4.1-all.zip` in the `/gradle` folder
  
**Note:** All the dependencies and Gradle are included in this repo (so it's big, ~300MB)

#### Offline template rebase instructions:

Step one - Build the dependency JARs:

1. Clone the corda repo or fetch the latest remote branches
2. Checkout the milestone release you want to create dependency JARs for
3. Run the gradle task `./gradlew buildCordappDependenciesZip`
4. Once the task has successfully completed the resulting zip can be found at `build/distributions/corda-deps-0.xx.x.zip`
5. Unzip it and save the JARs for later...

Step two - Get the offline template

1. Clone the cordapp-template-offline repo with `git clone http://github.com/roger3cev/cordapp-template-offline` or fetch the latest branches. There is only one branch, master.
2. Delete all of the JARs in `cordapp-template-offline/lib/dependencies` and then copy the new JARs in from step one
3. Open the project in IntelliJ as normal

Step three - Rebasing the code

1. Rebase as normal until there are no compilation errors

Job done!

TODO:

* Add a script to auto gather the dependencies as per http://stackoverflow.com/questions/28436473/build-gradle-repository-for-offline-development, as such there will be no need to manually gather the dependencies for each Corda Milestone release which is irritating/time consuming
* Add a switch to the `build.gradle` file which allows one to run a build in off-line or online mode - once this is in place we can merge this repo with the existing CorDapp template
