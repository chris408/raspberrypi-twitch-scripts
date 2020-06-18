#!/bin/bash

if [ "$(ps -ef | grep raspivid | wc -l)" -eq 1 ]; then
	/opt/vc/bin/raspivid -n -hf -vf -t 0 -w 1280 -h 720 -fps 10 -o - |  \
  ffmpeg -r 10 -re -i -  -codec copy -strict experimental  -threads 8 \
  -f flv "rtmp://live-sjc.twitch.tv/app/<twitch_api_token>" \
  -hide_banner -loglevel warning&
fi
