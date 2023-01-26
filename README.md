##### build the project

    ./gradlew build

##### build Docker image called java-app. Execute from root

    docker build -t java-app .
    
##### push image to repo 

    docker tag java-app demo-app:java-1.0
    


Gradle wrapper version upgraded from version 6.x to 7.0 
        
###### This will change the version in wrapper.settings

     ./gradlew wrapper --gradle-version 7.0

###### This will update the complete wrapper and download version 7.0 jar

     ./gradlew wrapper --gradle-version 7.0

In build.gradle file, replace:
- compile with implementation 
- testCompile with testImplementation

Because, version 7.0 removed compile and testCompile configurations.
Source: https://docs.gradle.org/current/userguide/upgrading_version_6.html#sec:configuration_removal

Please follow this post on how to push the project to Nexus
https://medium.com/@simionrazvan/how-to-create-a-gradle-library-and-publish-it-on-nexus-34be19b520aa

On a high level, two things are important here to push your repo to Nexus

###### Modify the build.gradle file to
###### A) define the jar to be published 
###### B) define the URL for the nexus repository location
###### C) define the name and password to access this nexus repository
###### rerun gradle clean build -./gradlew build and ./gradle publish
###### Login to Nexus dedicated user, browse the repository that you pushed. 
