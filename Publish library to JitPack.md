1. Remove unnecessary dependencies from the library module `build.gradle.kts` file
2. Add following code to the library module `build.gradle.kts` file:
```kotlin
plugins {  
    id("maven-publish")  
}

afterEvaluate {  
    publishing {  
        publications {  
            create<MavenPublication>("maven") {  
                from(components["release"])  
                groupId = "groupId"
                artifactId = "artifactId"  
                version = "version"  
            }  
        }    
    }
}
```
3. Create `jitpack.yml` file in root directory with following content:
```yml
jdk:  
  - openjdk17  
before_install:  
  - ./scripts/prepareJitpackEnvironment.sh
```
4. Push changes to GitHub
5. Create release
>[!warning] Be sure to specify the tag for the release
>The tag is used as a version for the library. So good name for release tag can be  `1.0.0` for example. See https://semver.org/ to get more about semantic versioning.
6. Visit https://jitpack.io/ website
7. In search field enter GitHub repository URL
8. Find the required tag (version) and click the "Get it" button

>[!tip] Fix 98% of all errors during the publication
>Just read logs carefully