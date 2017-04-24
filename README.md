![Corda](https://www.corda.net/wp-content/uploads/2016/11/fg005_corda_b.png)

# CorDapp Template: Offline Version

Versions supported: `M10.1`

This is a version of the CorDapp template which has been adapted for use on networks with limited
connectivity to the outside World!

Pre-requisites:

* You'll still need Oracle JDK 1.8
* You'll still want to download the latest version of IntelliJ IDEA CE (2017.1 at the time of writing)
* git

Changes made:

* Adapted `build.gradle` file which looks for all the Corda dependencies in the `/lib/dependencies` folder
* Adapted `gradle-wrapper.properties` file which looks for `gradle-3.4.1-all.zip` in the `/gradle` folder
  
**Note:** All the dependencies and Gradle are included in this repo.

TODO:

* Add a script to auto gather the dependencies as per http://stackoverflow.com/questions/28436473/build-gradle-repository-for-offline-development, as such there will be no need to manually gather the dependencies for each Corda Milestone release which is irritating/time consuming
* Add a switch to the `build.gradle` file which allows one to run a build in off-line or online mode - once this is in place we can merge this repo with the existing CorDapp template
