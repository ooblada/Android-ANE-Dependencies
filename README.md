# Android-ANE-Dependencies

Build Android dependencies for Adobe AIR ANEs

-------------

## Precompiled libraries
A set of precompiled ANEs are [available here](https://github.com/tuarua/Android-ANE-Dependencies/tree/master/anes) This includes Google Play Services and Android Support libraries

## Compiling your own libaries

You will need:
- Windows
- Android Studio 3.0+ installed
- AIR 29 SDK
- Powershell

Packages are described in [packages.xml](https://github.com/tuarua/Android-ANE-Dependencies/tree/master/build/scripts/packages.xml)   
The format follows closely the maven package descriptor   
Packages can be loaded from jcenter | maven | google   

Update AIR SDK path in [airsdk.config](https://github.com/tuarua/Android-ANE-Dependencies/tree/master/build/scripts/airsdk.config)  

Build single package
````shell
.\build.ps1 -package eventbus
`````



Example package  
https://mvnrepository.com/artifact/org.greenrobot/eventbus/3.0.0

````xml
<package name="eventbus">
    <groupId>org.greenrobot</groupId>
    <artifactId>eventbus</artifactId>
    <version>3.0.0</version>
    <type>jar</type>
    <repo>maven</repo>
    <category>misc</category>
    <dependencies></dependencies>
</package>
`````


Example package with child dependencies    
https://mvnrepository.com/artifact/com.google.firebase/firebase-config/16.0.0

````xml
<package name="firebase-config">
    <groupId>com.google.firebase</groupId>
    <packageName>com.google.firebase.config</packageName>
    <artifactId>firebase-config</artifactId>
    <version>16.0.0</version>
    <type>aar</type>
    <repo>google</repo>
    <category>firebase</category>
    <dependencies>
        <package name="firebase-abt">
            <groupId>com.google.firebase</groupId>
            <artifactId>firebase-abt</artifactId>
            <version>16.0.0</version>
            <type>aar</type>
            <repo>google</repo>
        </package>
    </dependencies>
</package>
`````
