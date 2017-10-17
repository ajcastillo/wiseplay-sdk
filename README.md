# Wiseplay SDK

[![](https://jitpack.io/v/lowlevel-studios/wiseplay-sdk.svg)](https://jitpack.io/#lowlevel-studios/wiseplay-sdk)

An Android library to integrate Wiseplay's video player and caster in third-party apps **(requires Wiseplay to be installed in the user's device)**.

## How to use

### Integrate the library in your project

You can easily integrate the library using Maven:

```
repositories {
    maven { url 'https://jitpack.io' }
}
 
dependencies {
    compile 'com.github.lowlevel-studios:wiseplay-sdk:1.1.0'
}
```

Or just add the .jar file in your project's ```libs``` folder.

### Launch the video player

The video player can be launched with just two lines of code:

```java
Media media = new Media("http://......");
Wiseplay.launch(context, media);
```

### Launch the video caster

To launch the video caster instead, just use the following call:

```java
Wiseplay.launchCast(context, media);
```

### Check if Wiseplay is available

The SDK provides a method to check if Wiseplay is available in the user's device:

```java
Wiseplay.isAvailable(context);
```

This method returns ```true``` if Wiseplay is available, otherwise it will return ```false```. If the latter, you can lead the user to install Wiseplay using the following method that will open the Play Store:

```java
Wiseplay.openStore(context);
```

### Check if the video caster is available

A method is also provided to check if the current installation of Wiseplay has support for the video caster:

```java
Wiseplay.isCastAvailable(context);
```

### Additional parameters

The library allows to set some additional parameters using the following methods that are available in the ```Media``` class. This overrides Wiseplay's user configuration:

```java
media.addHeader(String name, String value);
```
To add a HTTP header that will be sent in the network request.
```java
media.setHardwareAcceleration(boolean enable);
```
To enable or disable the hardware accelerated video playback.
```java
media.setImage(String image);
```
To set the video image (only used in the caster).
```java
media.setOpenSLES(boolean enable);
```
To enable or disable the hardware accelerated audio playback.
```java
media.setReferer(String url);
```
To set a referrer URL that may be required for some video links.
```java
media.setSubtitleUrl(String url);
```
To set the URL that points to the subtitle file to be loaded. It can point to a file stored in the device.
```java
media.setTitle(String title);
```
To set the video title.
```java
media.setVrFormat(VrFormat format);
```
To set the VR format of the video to be played.