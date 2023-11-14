README.MD
-------

1. What is the idea of the project?  - To develop a gradle plugin that is able to download, start and stop an Apache Tomcat server  


2. Prerequisites:  
2.1. Java version == 17  
2.2. Gradle version == 8.4  
2.3. A dummy application that will be used for testing.  
The dummy applicaiton needs a build.gradle file with the following settings:  
"  
plugins {  
    id 'gradle.plugin.tomcat.controller' version '0.1'  
}  

repositories {  
    mavenCentral()  
}  
  
apply plugin: 'gradle.plugin.tomcat.controller'  
"  
  
and a settings.gradle file:  
"  
pluginManagement {  
    repositories {  
        mavenLocal()  
        mavenCentral()  
    }  
}  
"  
  
3. Functionality offered by the plugin:  
3.1. Programatically start Apache Tomcat execute the following task: `./gradlew startTomcat -PrunTomcat=true` (accessible on http://localhost:9090)  
3.2. Start Apache Tomcat from a zip downloaded from 'https://repo1.maven.org/maven2/org/apache/tomcat/tomcat/'  
3.2.1. To start Apache Tomcat execute the following task: `./gradlew startTomcatZip` (accessible on http://localhost:8080)  
3.2.2. To stop Apache Tomcat execute the following task: `./gradlew stopTomcatZip -PstopTomcat=true`  


Notes:  
1. The programatically started apache tomcat runs with the latest 10.X version  
2. The Tomcat that is started from the zip runs with the latest version as described here - https://repo1.maven.org/maven2/org/apache/tomcat/tomcat/maven-metadata.xml  
