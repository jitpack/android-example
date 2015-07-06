# android-example

[![Release](https://img.shields.io/github/release/jitpack/android-example.svg?label=maven version)](https://jitpack.io/#jitpack/android-example)

Example Android library project that works with jitpack.io. The 
See also the guide for [building Android projects](https://github.com/jitpack/jitpack.io/blob/master/ANDROID.md)

https://jitpack.io/#jitpack/android-example/1.0.2

Add it to your build.gradle with:
```gradle
repositories {
    jcenter()
    maven { url "https://jitpack.io" }
}
```
and:

```gradle
dependencies {
    compile 'com.github.jitpack:android-example:1.0.2'
}
```

## Multiple build variants

If your library uses multiple flavours then see this example:
https://github.com/jitpack-io/android-jitpack-library-example

## Adding the maven plugin

To enable installing into local maven repository and JitPack you need to add the [android-maven](https://github.com/dcendents/android-maven-plugin) plugin:

1. Add `classpath 'com.github.dcendents:android-maven-gradle-plugin:1.3'` to root build.gradle under `buildscript { dependencies {`
2. Add `com.github.dcendents.android-maven` to the library/build.gradle

After these changes you should be able to run:

    ./gradlew install
    
from the root of your project. If install works and you have added a GitHub release it should work on jitpack.io

## Adding a sample app 

If you add a sample app to the same repo then your app needs to have a dependency on the library. To do this in your app/build.gradle add:

```gradle
    dependencies {
        compile project(':library')
    }
```
