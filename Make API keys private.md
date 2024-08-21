#Security

1. Define API keys in root `local.properties` file:
```properties
# Replace it with your api key
API_KEY=a1b2c33d4e5f6g7h8i9jakblc
```
2. Import API keys in module `build.gradle.kts` file:
```kotlin
import java.util.Properties

android {  
    defaultConfig {   
        val properties = Properties()
        properties.load(project.rootProject.file("local.properties").inputStream())  
        buildConfigField(  
            type = "String",  
            name = "API_KEY",  
            value = "\"${properties.getProperty("API_KEY")}\"",  
        )   
    }

	buildFeatures {  
	    buildConfig = true  
	}
}
```
3. Use it in your code:
```kotlin
private val apiKey = BuildConfig.API_KEY
```