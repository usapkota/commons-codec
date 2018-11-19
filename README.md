
     
## Update on the original code from [Apache Commons Codec](https://github.com/apache/commons-codec).

# apache-commons-codec-android
This is a "shaded" version of [Apache Commons Codec](https://github.com/apache/commons-codec) for Android use, which is accomplished using [Apache Maven Shade Plugin](http://maven.apache.org/plugins/maven-shade-plugin/index.html).

## Why?
This is a common problem faced by Android developers because of Android framework using an old version ( I think its v1.3) of commons-codec.
If you force yourself to use only methods included in older versions, then you will not get "Could not find method" errors, however if you want to use new methods which were added in
newer versions ( like all normal developers) then you will get "Could not find method" errors. There are a handful of ways to fix/get around this error.
I decided to use Apache Maven Shade plugin to rename packages from the original source code.

## How?
First I forked the code for Apache Commons Codec from [GitHub](https://github.com/apache/commons-codec)
and added the Shade Plugin on the pom.xml. After updating the pom file, build your project and add the jar file of this shaded project on your Android project.
If you want you can also download this project, build it and use the jar (commons-codec-android-1.12-SNAPSHOT.jar) in your project. You can also see in my pom file (line:323), I have renamed 'org.apache.commons' as 'org.apache.commons.android'. Therefore instead of importing packages as 'org.apache.commons.*', 
you will have to import as 'org.apache.commons.android.*'.


By Ujwal Sapkota.

