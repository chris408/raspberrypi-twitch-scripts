# Twitch as a web camera streaming service
This repo has a script I'm using to setup a Raspberry pi stream using the v2 camera module. 

## Directions
Put `streamit` in /usr/local/bin, and then make it executable with `chmod +x /usr/local/bin/streamit`

Next, setup a cron job that will run `streamit` once per minute. This is required because sometimes the twitch server will error out and drop your ffmpeg clinet. Note: your subscribers will be spammed with a live stream started notification each time your twitch webcam crashes and restarts.

Run
`crontab -e`

Then add a new crontab with:

`1-59 * * * * /usr/local/bin/streamit`

I've had this running for about a month at this point with fairly good results. The script limits the resolution to 720 with 10 frames per second amd has audio disabled (my camera is behind a window). The CPU usage is low and it seems pretty stable. I didn't have much luck with 1920x1080, as I noticed frames dropping and the stream would hang or not start. Let me know if you find a configuration that streams 1920x1080 smoothly on a Raspberry Pi B+.
