# raspberrypi-setup
:raspberry:

# RealVNC
https://www.realvnc.com/en/connect/docs/raspberry-pi.html#raspberry-pi-connect-direct
https://support.realvnc.com/knowledgebase/article/view/541/0/how-do-i-enable-the-experimental-direct-capture-feature-from-the-command-line

# FFMPEG + IMAGEMAGICK

https://gist.github.com/adddog/d82581faf10d666d35b9771eaa65d5ac

# iOS webcam streaming

[CamofWeb](https://alfred.camera/woc/#)

Fps is around 14-16 (iPhone 4)

### shell command

`ffmpeg -f image2pipe -framerate 15 -vcodec mjpeg -i "http://192.168.1.76:8080/video.jpeg" -g 15 -r 15 -framerate 15  -vsync 0  -movflags +faststart  -preset ultrafast -tune zerolatency -c:v libx264 -b:v 800k -minrate 400k  -maxrate 1000k -bufsize 3000k  -an -analyzeduration 256 -probesize 64  -f mpegts - | omxplayer -b -r --no-keys -s -I -z --timeout 60 --live -o hdmi  pipe:0`
