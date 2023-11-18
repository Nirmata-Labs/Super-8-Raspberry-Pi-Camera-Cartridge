# Super-8-Raspberry-Pi-Camera-Cartridge
Retro-Fit-Solution for Super 8 Cameras


## Create a RTSP-Stream for debugging

Install VLC on Raspberry:
```
sudo apt-get update
sudo apt-get install vlc
```

Start RTSP-Stream (FPS18 is working best for my camera):
```
raspivid -o - -t 0 -n -w 640 -h 480 -fps 18 | cvlc -vvv stream:///dev/stdin --sout '#rtp{sdp=rtsp://:8554/}' :demux=h264
```

Open the RTSP-Networkstream on a PC, e.g. in VLC-Mediaplayer:
```
rtsp://<ip-adress-of-raspi>:8554/
```
