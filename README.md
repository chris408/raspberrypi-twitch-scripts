# raspberrypi-twitch-scripts
This repo has a script I'm using to setup a Raspberry pi with the v2 camera module twitch stream.

## Directions
Put `streamit` in /usr/local/bin, and then make it executable with `chmod +x /usr/local/bin/streamit`

Next, setup a cron job that will run streamit.sh once per minute. This is required because sometimes the twitch server will error out and drop your ffmpeg clinet. 

`crontab -e`

`1-59 * * * * /usr/local/bin/streamit`

I've had this running for about a month now with fairly good results. The script limits the resolution to 720 with 10 frames per second. The CPU usage is low and it seems pretty stable. 
