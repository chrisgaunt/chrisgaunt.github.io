---
layout: post
title: SmoothFollowCamera2D v1.0.0
---
SmoothFollowCamera2D is now at v1!
I feel it's now ready to be used in real projects, and I'll be using it in my own games.

The changes since the last version are:

* Added options to enable/disable all min/max limits individually.
* Now using <a href="http://docs.unity3d.com/ScriptReference/Vector3.SmoothDamp.html" target="_blank">Vector3.SmoothDamp</a> for the smooth movement calculation.
* Renamed from SmoothCamera2D to SmoothFollowCamera2D to be clearer on what it is.
* Renamed min/max & limit variables.

<!-- more -->

<p class="message">
  <a href="https://github.com/chrisgaunt/SmoothFollowCamera2D" target="_blank">SmoothFollowCamera2D on GitHub</a> (includes example scenes)
</p>

Feel free to use this script in your games.<br>
If you do use this script I would love to know how you've used it.

### SmoothFollowCamera2D

Here's the camera without any X & Y position limits set.<br>
Notice how it shows the blue space behind the level.

<div id="unityPlayer1" class="unity-player" style="height:200px;width:270px;">
  <div class="missing">
    <a href="http://unity3d.com/webplayer/" title="Unity Web Player. Install now!">
      <img alt="Unity Web Player. Install now!" src="http://webplayer.unity3d.com/installation/getunity.png" width="193" height="63" />
    </a>
  </div>
  <div class="broken">
    <a href="http://unity3d.com/webplayer/" title="Unity Web Player. Install now! Restart your browser after install.">
      <img alt="Unity Web Player. Install now! Restart your browser after install." src="http://webplayer.unity3d.com/installation/getunityrestart.png" width="193" height="63" />
    </a>
  </div>
</div>

<div class="unity-message">Click on the game window and use the arrow keys to move around.</div>

Here's the camera with limits set.

<div id="unityPlayer2" class="unity-player" style="height:200px;width:270px;"></div>

<div class="unity-message">Examples were created with <a href="http://unity3d.com/unity/" title="Go to unity3d.com" target="_blank">Unity</a> and 2D art by <a href="http://www.kenney.nl/" target="_blank">Kenney</a></div>

<p class="message">
  <a href="https://github.com/chrisgaunt/SmoothFollowCamera2D" target="_blank">SmoothFollowCamera2D on GitHub</a> (includes example scenes)
</p>

<script type="text/javascript">
<!--
var unityObjectUrl = "http://webplayer.unity3d.com/download_webplayer-3.x/3.0/uo/UnityObject2.js";
if (document.location.protocol == 'https:')
  unityObjectUrl = unityObjectUrl.replace("http://", "https://ssl-");
document.write('<script type="text\/javascript" src="' + unityObjectUrl + '"><\/script>');
-->
</script>
<script type="text/javascript">
<!--
  var config = {
    width: 270,
    height: 200,
    params: { enableDebugging:"0" }

  };
  var u1 = new UnityObject2(config);
  var u2 = new UnityObject2(config);

  jQuery(function() {

    var $missingScreen = jQuery("#unityPlayer1").find(".missing");
    var $brokenScreen = jQuery("#unityPlayer1").find(".broken");
    $missingScreen.hide();
    $brokenScreen.hide();

    u1.observeProgress(function (progress) {
      switch(progress.pluginStatus) {
        case "broken":
          $brokenScreen.find("a").click(function (e) {
            e.stopPropagation();
            e.preventDefault();
            u1.installPlugin();
            return false;
          });
          $brokenScreen.show();
        break;
        case "missing":
          $missingScreen.find("a").click(function (e) {
            e.stopPropagation();
            e.preventDefault();
            u1.installPlugin();
            return false;
          });
          $missingScreen.show();
        break;
        case "installed":
          $missingScreen.remove();
        break;
        case "first":
        break;
      }
    });
    u2.initPlugin(jQuery("#unityPlayer2")[0], "/public/posts/2014-07-18-smooth-follow-camera-2D-v1.0.0/with_limits.unity3d");
    u1.initPlugin(jQuery("#unityPlayer1")[0], "/public/posts/2014-07-18-smooth-follow-camera-2D-v1.0.0/without_limits.unity3d");
  });
-->
</script>
