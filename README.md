# IntelliJ IDEA Community Edition [![official JetBrains project](http://jb.gg/badges/official.svg)](https://confluence.jetbrains.com/display/ALL/JetBrains+on+GitHub)
### Building and Running from the IDE
To develop IntelliJ IDEA, you can use either IntelliJ IDEA Community Edition or IntelliJ IDEA Ultimate not older than 2017.3. To build and run the code:
* Run **getPlugins.sh** / **getPlugins.bat** from the project root directory to check out additional modules.
* If this git repository is not on 'master' branch you need to checkout the same branches/tags in android and android/tools-base git repositories.
* Open the project.
* If an error notification about a missing required plugin (e.g. Kotlin) is shown enable or install that plugin.
* Configure a JSDK named "**1.8**", pointing to an installation of JDK 1.8.
  * Add <JDK_18_HOME>/lib/tools.jar to the set of "**1.8**" JARs.
* Configure a JSDK named "**IDEA jdk**" (case sensitive), pointing to an installation of JDK 1.6.
  * If you don't plan to edit modules which use "IDEA jdk" you can configure "IDEA jdk" to point to the same installation of JDK 1.8 as "1.8" JDK. 
  * Unless you're running on a Mac with an Apple JDK, add <JDK_HOME>/lib/tools.jar to the set of "**IDEA jdk**" JARs.
* If 'Maven Integration' plugin is disabled add path variable 'MAVEN_REPOSITORY' pointing to '<USER_HOME>/.m2/repository' directory (File | Settings | Appearance & Behavior | Path Variables).
* Use Build | Build Project to build the code.

To run the IDE from the built code
* use the provided shared run configuration "**IDEA**".

To run tests apply these setting to the **default** JUnit run configuration type:
* Working dir: 
  `<IDEA_HOME>\bin`
* VM parameters: 
  `-ea -Xmx128M -Djava.system.class.loader=com.intellij.util.lang.UrlClassLoader -Didea.config.path=../test-config -Didea.system.path=../test-system`
  
To build an installation packages, run `ant` command in `<IDEA_HOME>` directory. See build.xml file for details.  

You can find other useful information at [http://www.jetbrains.org](http://www.jetbrains.org). [Contribute section](http://www.jetbrains.org/display/IJOS/Contribute) of that site describes how you can contribute to IntelliJ IDEA.