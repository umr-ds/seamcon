---
layout: post
title: Install Apps
---

After installing the MPTCP kernel, you have to install two apps. The first one is for being able to enable the Wi-Fi and cellular interface at the same time. The second app is the demonstator app itself.

Checkout the MPTCPControl app.

```
git clone https://github.com/umr-ds/seamcon-mptcpcontol.git
```

Import it into Android Studio and install it on your device. Within the app itself there is not much to do. Just make sure that the slider is enabled and grant root permissions when asked.

Then, checkout the demo app and make sure you are on the master branch.

```
git clone https://github.com/umr-ds/seamcon-SeamlessDemo.git
```

Again, import this to Android Studio. This time you have to do some modifications. In `DatabaseHelper.java` you have to provide a HTTP server, where logged prediction data is pushed to. The line looks like the following:

```java
String uploadServerBaseURL = "http://ds.mathematik.uni-marburg.de/seamless-upload/upload/";
```

Additionally, you have to specify the URL of the video stream, which was set up in the previous step. This is done in `MainActivity.java` line 212:

```java
geckoSession.loadUri("http://dsgw.mathematik.uni-marburg.de:5000/?experimentid=" + encodedUrl);
```

*(Optional) You also can replace the classifier model. How this is done you can see in [this guide](index#setup-and-reproduction)*

After these modifications install the app. When asked, grant root permissions.

You are done here. Head over to the [main page and see how it continues](index#install-the-entire-experiment-stack).
