# httpclient-android [![Build Status](https://travis-ci.org/smarek/httpclient-android.svg)](https://travis-ci.org/smarek/httpclient-android)

Build script and dependencies to create repackaged upstream version of HttpClient and depdendencies (HttpMime, HttpCore, HttpClient-Cache) and get it working on Android API version from 3 to 23

Download the repository and simply hit `./build.sh` script

Required dependencies are:
  - JDK 6 or newer
  - Gradle 2.4 or newer
  - `find`, `grep`, `svn` and `sed` (or `gsed` for OS X)
  - for Kerberos support you need `Android NDK`, `git` and `swig`

Build params (ENV variables) you can use:
  - `UPSTREAM_VER` (default is current version of Apache HttpClient libraries, eg. `4.3.3`)
  - `UPDATE_UPSTREAM`, whether the build script should download SVN/GIT/... sources again (useful for recurring builds)
  - `SED_CMD` used variant of SED utility (default is `sed -i` on linux and `gsed -i` on Mac OS X)
  
This repository version will publish the library under namespace `cz.msebera.android.httpclient`

Using `gradle installArchives` will install the library to local Maven repository

Current version: **4.3.3** (originating from upstream HttpClient 4.3.3 version)

Gradle dependency string, after having it installed

```gradle
dependencies {
  compile "cz.msebera.android.httpclient:httpclient-android:4.3.3"
}
```

Or you can simply depend on it as on Gradle library, after `build.sh` script finishes successfully, like this:
```gradle
dependencies {
  compile project("httpclient-android")
}
```
