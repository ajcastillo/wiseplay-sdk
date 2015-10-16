# Wiseplay SDK

An Android library to allow the use of Wiseplay's video player in third-party apps.

## How to use

### Integrate the library in your project

Just add the .jar file in your project's ```libs``` folder.

### Launch the video player

The video player can be launched with only these two lines of code:

```java
Wiseplay.Media media = new Wiseplay.Media("http://......");
Wiseplay.launch(context, media);
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

### Additional parameters

The library allows to set some of the video player's parameters using the following methods that are available in the ```Wiseplay.Media``` class. This overrides Wiseplay's user configuration:

```java
media.setHardwareAcceleration(boolean enable)
```
To enable or disable the hardware accelerated video playback
```java
media.setOpenSLES(boolean enable)
```
To enable or disable the hardware accelerated audio playback
```java
media.setReferer(String url)
```
To set a referrer URL that may be required by some video links
```java
media.setSubtitleUrl(String url)
```
To set the URL that points to the subtitle file to be loaded. It can point to a file stored in the device
