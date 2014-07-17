---
layout: post
title: SmoothCamera2D v0.1
---

I'm going to start as I mean to go on and get right into things by sharing a C# script I made for Unity.

Disclaimer: I am learning C# and this was a result of my studies, so there may well be better ways to do this. I would be grateful for any suggestions on how to improve it.

<p class="message">
  <a href="https://github.com/chrisgaunt/SmoothCamera2D" target="_blank">SmoothCamera2D on GitHub</a> (includes example scenes)
</p>

Feel free to use this script in your games or as a starter script to build your own camera.

### SmoothCamera2D

I've been following several tutorials, reading forums and playing around with example code, but couldn't find the exact kind of chase camera I wanted for my first platformer.
There's a SmoothFollow.js standard asset, but after trying it out I realized it was for 3D.
Rather than try to modify the js script I decided to make my own in C#, taking advice from several tutorials and forums.

The criteria for my camera were:

- Follow the player in all directions (up, down, left, right), trying to keep the player in the center of the view.
- Smoothly catch up to the player once they are a certain distance away (configurable).
- Optionally, stop moving if the camera hits certain X & Y min/max positions.

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

Here's the camera with limits set.<br>Just how I wanted it!

<div id="unityPlayer2" class="unity-player" style="height:200px;width:270px;"></div>

<div class="unity-message">Examples were created with <a href="http://unity3d.com/unity/" title="Go to unity3d.com" target="_blank">Unity</a> and 2D art by <a href="http://www.kenney.nl/" target="_blank">Kenney</a></div>

If you do use this script I would love to know how you used it.

<p class="message">
  <a href="https://github.com/chrisgaunt/SmoothCamera2D" target="_blank">SmoothCamera2D on GitHub</a> (includes example scenes)
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
    u2.initPlugin(jQuery("#unityPlayer2")[0], "/public/posts/2014-07-16-smoothcamera2d-v0.1/with_limits.unity3d");
    u1.initPlugin(jQuery("#unityPlayer1")[0], "/public/posts/2014-07-16-smoothcamera2d-v0.1/without_limits.unity3d");
  });
-->
</script>
