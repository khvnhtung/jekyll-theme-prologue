---
title:  "How to install and run Electron on your Raspberry Pi"
date:   2019-03-14 16:55:32
categories: tutorial
---

An easy tutorial on how to install and run Electron on your Raspberry Pi  
Tested on Raspberry Pi 3B running Raspbian Stretch.  

First, you will need open the terminal and type in each commands.  
```bash
cd /tmp
wget https://nodejs.org/dist/v10.15.3/node-v10.15.3-linux-armv7l.tar.xz
tar xfv node-v10.15.3-linux-armv7l.tar.xz
cd node-v10.15.3-linux-armv7l
sudo cp -R * /usr/local/
```
Now proceed to download and install Electron..



```bash
sudo npm install -g electron --unsafe-perm=true --allow-root
```
And if you want to test it, install the Electron quick start app.
```bash
# Clone this repository
git clone https://github.com/electron/electron-quick-start
# Go into the repository
cd electron-quick-start
# Install dependencies
npm install
# Set display
export DISPLAY=:0
# Run the app
npm start
```
And if you ever run into an issue when using Electron 4 app that said  
```/lib/arm-linux-gnueabihf/libc.so.6: version `GLIBC_2.27' not found```  
then until Raspbian 10 is released with glibc 2.28, the only way I'm aware of to install and run a working Electron version on a Raspberry Pi running Raspbian Stretch is:  
```bash
sudo npm install -g electron@3.0.13 --unsafe-perm=true --allow-root --arch=armv7l --platform=linux
```  
In your app package.json, make sure electron 3.0.13 is required, otherwise you will get the dreaded glibc 2.27 version error.  
This means you are running a Chromium 66 engine. I hope this info helps someone.  

credits:  
https://github.com/electron/electron/issues/16205  
https://blog.marekkraus.sk/linux/how-to-make-electron-run-on-raspberry-pi/