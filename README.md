PhoneGap/Android
================
PhoneGap/Android is an Android application library that allows for PhoneGap based projects to be built for the Android Platform. PhoneGap based applications are, at the core, an application written with web technology: HTML, CSS and JavaScript. 

Pre Requisites
--------------
- Java JDK 1.5
- Android SDK Package [http://developer.android.com](http://developer.android.com)
- Apache ANT
- Ruby (Optional, see section: DroidGap with JRuby)

Install
-------

Add PhoneGap/Android to your PATH variable like so:

    export PATH=$PATH:~/phonegap-android/bin

DroidGap: PhoneGap/Android Dev Script
-------------------------------------

Useful utilities for developers building mobile apps using PhoneGap for Android.

Usage:

<pre>droidgap [command] [parameters]</pre>

Commands:    

<pre>
help ... See this message. Type help [command name] to see specific help topics.
gen .... Generate an example PhoneGap application to current directory.
pkg .... Creates an Android compatible project from a www folder. Careful, this clobbers previous packaging.
run .... Installs a valid PhoneGap Project to first device found.
log .... Attach a logger that listens for console.log statements.
ship ... Build and sign an APK suitable for submission to an Android Marketplace.
</pre>

Quickstart:

<pre>
    $ droidgap gen example 
    $ cd example
    $ droidgap run
</pre>

Launch your app and start a logger with:

<pre>
    $ droidgap log
</pre>

DroidGap with JRuby
-------------------

If you want to use the droidgap command but do not want to install Ruby then you can call it using jruby jar included in the lib folder. All the options are the same and a call looks like this:

    java -jar jruby-complete-1.4.0RC1.jar ../bin/droidgap help run
    
Keep in mind this will be slower due to JVM warmup.

Importing a PhoneGap/Android app into Eclipse
---------------------------------------------

1. File > New > Project...
2. Android > Android Project
3. Create project from existing source (point to the generated app). This should import the project into Eclipse. Almost done!
4. Right click on libs/phonegap.jar and add to build path.
5. Right click on the project root: Run as > Run Configurations
6. Click on the Target tab and select Manual (this way you can choose the emulator or device to build to).


Common Command Line Tasks
=========================

Running Mobile Spec
---

TODO need content here
    
Compile an APK
---

Converting a W3C Widget into a an APK
---

    $ ./droidgap

List devices attached
---

    $ adb devices 
    List of devices attached 
    0123456789012	device

Install APK onto device
---

    $ apk -s 0123456789012 install phonegap.apk
    
Logging 
---

Via console.log calls from your apps javascript.

    $ adb logcat
    
Debugging
---
    
Attach it to a process on the device

    $ adb jdwp
    adb forward tcp:8000 jdwp: jdb -attach localhost:8000
    
    
For more info see
-----------------
- [http://docs.phonegap.com](http://docs.phonegap.com)
- [http://wiki.phonegap.com](http://wiki.phonegap.com)