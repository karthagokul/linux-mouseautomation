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

Write a Small Script like the one available in the respository
