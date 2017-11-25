# linux-mouseautomation
A Utility Script to Automate Mouse Events in Linux
# Usecase
I was participating in a Website Survey and the usecase was below

1. A Website contains a links to Other website 
2. We need to click on a Visit Button which opens another browser tab
3. A timer Counts 20 seconds of your visiting time and you can earn some points ;)
4. Close the New tab, Come back to parent website and refresh thepage and do the same over again.

# How did I automate this ?
Ubuntu comes with a Handy tool Named xdotool to simulate X mouse events
Download Xdotools using the below command
sudo apt-get install xdotools

Using xdotools find your mouse hotspots like below
xdotool getmouselocation

Note this down and 

Write a Small Script like below

#refresh
#x:136 y:75 screen:0 window:54525953

#hit
#x:349 y:468 screen:0 window:54525953

#next tab
#x:360 y:38 screen:0 window:54525953

#close button
#x:446 y:39 screen:0 window:54525953

#prevtab
#x:167 y:39 screen:0 window:54525953

#leavepopup if any
#x:884 y:181 screen:0 window:54525953

#!/bin/bash

while [ 1 ]; do
#do a click
  xdotool mousemove 349 468 click 1 &
  xdotool mousemove 349 493 click 1 &
#go to new tab
  xdotool mousemove 360 38 click 1 &
#wait
  sleep 25
#go to nprev tab after closing
  xdotool mousemove 446 41 click 1 &
  sleep 2
  #xdotool mousemove 884 181 click 1 &
  xdotool mousemove 167 39 click 1 &
#refresh
  xdotool mousemove 136 75 click 1 &
  sleep 10
done
