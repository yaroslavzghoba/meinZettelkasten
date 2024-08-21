# Installation
1. Define dependencies in your `libs.version.toml` file:
```toml
[versions]
paging = "3.3.0"

[libraries]
paging-runtime = { group = "androidx.paging", name = "paging-runtime", version.ref = "paging" }  
paging-compose = { group = "androidx.paging", name = "paging-compose", version.ref = "paging" }
```
>[!info] See [Paging artifact at MVN Repository](https://mvnrepository.com/artifact/androidx.paging/paging-runtime) to get last version.

2. Implement it in your module-level `build.gradle.kts` file:
```kotlin
dependencies {  
    implementation(libs.paging.runtime)  
    implementation(libs.paging.compose)  // Optionally. Compose integration
}