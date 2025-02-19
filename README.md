# android-example

[![Release](https://jitpack.io/v/jitpack/android-example.svg)](https://jitpack.io/#jitpack/android-example)

Example Android library project that works with jitpack.io.

See this [Tutorial](https://medium.com/@ome450901/publish-an-android-library-by-jitpack-a0342684cbd0) on how to publish an Android Library with JitPack.

For more details check out the [documentation](https://docs.jitpack.io/android/)

https://jitpack.io/#jitpack/android-example

Add it to your settings.gradle with:
```gradle
	dependencyResolutionManagement {
		repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
		repositories {
			mavenCentral()
			maven { url 'https://jitpack.io' }
		}
	}
```
and:

```gradle
dependencies {
    implementation 'com.github.jitpack:android-example:{latest version}'
}
```

## Multiple build variants

If your library uses multiple flavours then see this example:
https://github.com/jitpack-io/android-jitpack-library-example

## Adding the maven plugin

To enable installing into local maven repository and JitPack you need to add the [maven-publish](https://developer.android.com/studio/build/maven-publish-plugin) plugin:

Then add the publishing section to your library build.gradle:
```gradle
publishing {
  publications {
    release(MavenPublication) {
      groupId = 'com.my-company'
      artifactId = 'my-library'
      version = '1.0'

      afterEvaluate {
        from components.release
      }
    }
  }
}
```

After these changes you should be able to run:

    ./gradlew publishToMavenLocal
    
from the root of your project. 
If `publishToMavenLocal` works and you have added a GitHub release it should work on jitpack.io

## Adding a sample app 

If you add a sample app to the same repo then your app needs to have a dependency on the library. To do this in your app/build.gradle add:

```gradle
    dependencies {
        compile project(':library')
    }
```
