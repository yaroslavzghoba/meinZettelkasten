#Exception

Occurs when trying to use Composable functions in a newly created module.
```
org.jetbrains.kotlin.backend.common.BackendException: Backend Internal error: Exception during IR lowering
```
To fix this problem add following code to the module `build.gradle.kts` file:
```kotlin
android {
	buildFeatures {
       compose = true
    }
    composeOptions {
       kotlinCompilerExtensionVersion = "VERSION"  // replace it
    }
}
```
>[!tip] Compose version
>You can copy the version from the appropriate block in the `app` module