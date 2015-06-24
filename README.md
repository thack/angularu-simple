# AngularU Simple

### Obectives

* Make sure all requirements are installed.
* Demonstrate iOS simulator and Android emulators.
* Create a simple application.
* Modify Cordova configuration.

### Step 1

* Install Ionic and Cordova
    * ``npm install -g ionic cordova``

### Step 2

* Create new project
    * ``ionic start simple blank``
    * ``cd simple``
    * ``ionic platform add ios`` (Should be automatic on OSX)
    * ``ionic platform add android``

### Step 3

* Run on emulator or device
    * iOS recommended:
        * ``ionic emulate ios -l -c``
        * Live reload and console output.
    * Android recommended (Device or Genymotion):
        * ``ionic run android -l -c``
        * Live reload and console output.
    * ``ionic run ios``
        * Can be tricky because of certificate security
    * ``ionic emulate android``
        * Slow without HAXM. HAXM is buggy on Mac.

### Step 4

* Change title to Ionic Video
```
<ion-header-bar class="bar-stable">
  <h1 class="title">Ionic Video</h1>
</ion-header-bar>
```

* Add .video-container div and iframe inside the already present <ion-content> tag:
```
    <div class="video-container">
      <iframe src="http://www.youtube.com/embed/JAUoeqvedMo?rel=0" frameborder="0" allowfullscreen></iframe>
    </div>
```

* Add CSS for .video-container div
```
  .video-container {
    position: relative;
    padding-bottom: 56.25%;
    padding-top: 30px;
    height: 0;
    overflow: hidden;
  }

  .video-container iframe,
  .video-container object,
  .video-container embed {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
```

### Step 5

* Add Crosswalk
    * ``ionic browser add crosswalk``
* Run again on Android:
    * ``ionic run android``

### Step 6

* Launch in landscape. Modify Cordova config.xml:
```
  <preference name="orientation" value="landscape" />
```

* Remove ion-header-bar.
* Modify CSS as necessary.

### Extra Credit

* Add a content-security-policy for Cordova v5 or better.
* Add $sceDelegateProvider.resourceUrlWhitelist.
