# minimal-android-project

This repository explores how simple it can be to set up a valid,
working Android project. You will need:

* One `.java` activity source file, placed in its appropriate package
  directory
* One `AndroidManifest.xml`
* One `build.gradle`
  * Certainly this is optional, as you can build the project using
    command line tools from the Android SDK. But let's not complicate
    things unnecessarily.

For more in-depth information about this repository, see
[my blog post](http://czak.pl/2016/01/13/minimal-android-project.html).

## How to build

```
$ git clone https://github.com/czak/minimal-android-project.git
$ gradle installDebug
```

The app will be installed on all devices accessible to `adb`.

## Notes

[Gradle Wrapper]: https://gradle.org/docs/current/userguide/gradle_wrapper.html
[build.gradle]: build.gradle

This project makes a few assumptions about your environment in order
to build correctly:

* You have `gradle` 2.10 installed - there is no [Gradle Wrapper][]
  included.
* You have `JAVA_HOME` set up. If you have `java` in your path, you
  should be good to go.
* You have `ANDROID_HOME` set to the root folder of your Android SDK
  installation.
* SDK and build tools versions are hardcoded in [build.gradle][] to
  `23` and `23.0.2`, respectively.

Additionally, the folder structure relies on the source set convention
expected by the Gradle Android plugin:

```
project
 ├── build.gradle
 └── src
     └── main
         ├── AndroidManifest.xml
         └── java
             └── pl
                 └── czak
                     └── minimal
                         └── MainActivity.java
```

## Contact

Suggestions on how to minimize this further are welcome!
