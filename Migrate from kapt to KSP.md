1. Add plugin to the `libs.versions.toml` file:
```toml
[versions]
ksp = "VERSION"

[plugins]
ksp = { id = "com.google.devtools.ksp", version.ref = "ksp" }
```
>[!warning] Version for KSP
>The KSP version consists of the Kotlin version (first part) and the KSP version itself (second part), `1.9.0-1.0.13` for example. **You must use a version of KSP where the Kotlin version is the same as the Kotlin version in your project**. See [KSP Releases page on GitHub](https://github.com/google/ksp/releases) or [artifact at MVN Repository](https://mvnrepository.com/artifact/com.google.devtools.ksp/symbol-processing-api?repo=central) to find a compatible version. 

2.  Declare the KSP plugin in your top level `build.gradle.kts` file:
```kotlin
plugins {
	alias(libs.plugins.ksp) apply false
}
```
3. Then, enable KSP in your module-level `build.gradle.kts` file:
```kotlin
plugins {
	alias(libs.plugins.ksp)
}
```
4. Replace annotation processors with KSP
>[!info] Supported libraries
>Some of the libraries do not support KSP. Check the [list of supported libraries](https://kotlinlang.org/docs/ksp-overview.html#supported-libraries) to learn more.