1. Add dependency to your `libs.versions.toml` file:
```toml
[versions]
datastore = "1.1.1"

[libraries]
datastore-preferences = { group = "androidx.datastore", name = "datastore-preferences", version.ref = "datastore" }
```
2. Implement it in your module `build.gradle.kts` file:
```kotlin
dependencies {  
    implementation(libs.androidx.datastore.preferences)
}
```
3. Create a repository that will 