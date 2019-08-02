---
title:  "Play sound when Macbook charger is connected (for 2015 macs and earlier)"
date:   2019-06-28 10:13:18
categories: tutorial
---

Here are the tutorial to enable sound (similar to iPhone when is plugged to a charger) for a Macbook.
Please also know that this tutorial will only work for macs below 2015 since macs that are made from 2016 above all have the sound to play by default)

In Terminal, copy and paste this in if you want to play sound when the charger is connected.
```
defaults write com.apple.PowerChime ChimeOnAllHardware -bool true; open /System/Library/CoreServices/PowerChime.app &
```
If you don't want to hear this sound anymore, simply disable it by this command.
```
defaults write com.apple.PowerChime ChimeOnAllHardware -bool false;killall PowerChime
```