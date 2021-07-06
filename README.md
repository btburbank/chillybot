# Fork of chillybot

*Credits*
This bot uses the turntable api by alain gilbert which can be found here:

https://github.com/alaingilbert/Turntable-API

this bot is a fork of btburbank's chillybot

## Contents: 

[1. Features](https://github.com/jaycammarano/chillybot#features)

[2. Quick Start](https://github.com/jaycammarano/chillybot#quick-start)

[3. Linux Bonus Instructions](https://github.com/jaycammarano/chillybot#linux-bonus-instructions)

[3.a Running the bot in the background using screen](https://github.com/jaycammarano/chillybot#running-the-bot-in-the-background--using-screen)

[3.b Auto-restarting the Bot on Crash Using Systemd](https://github.com/jaycammarano/chillybot#auto-restarting-the-bot-on-crash-using-systemd)

## chillybot Features
Features
---------------

Queue

afk limit

afk audience limit(separate from afk limit, both can be toggled on and off)

song length limit

ban list

song play limit

vote skipping

room greeting

add songs to your bots playlist

randomize your bots playlist

Vip list (for when special guests come to dj)

autodjing when 3 or less djs or when no djs on stage

skips stuck songs and gives others 20 seconds to skip

very noninstrusive, only enforces the queue when people are in the queue
(very easy to make it enforce it all the time, just ask)

ability to toggle just about everything
very easy to use! entirely script based just download node, run the script and your off!


For a full list of commands, please consult the commands.txt file(does not contain all features, just commands).


This is a bot for straight chillin on turntable.fm but the code can be used in any room.
If you notice any bugs or have any questions, comments, or concerns feel free to open an issue
and i will try to respond.

## Quick Start:
1. download node.js from nodejs.org

2. download dependancys(the turntable api) by opening up command prompt and typing in `npm install` in the same directory that you will be running the script from.

3. create a new account on turntable.fm, this will be your bot. login as the bot and enter the room you want the bot in

4. get its user id and auth, and roomid and enter that into the script in the setup section
   make sure that you do this in the room that you want the bot to show up in as every room 
   has a different room id. In order to find this information out add [this bookmarklet](http://alaingilbert.github.io/Turntable-API/bookmarklet.html) to
   your bookmark bar and use it in the room logged in as the bot 

5. Rename `.env copy` to `.env`, make sure there is not space at the end of the filename

6. Fill out `.env` with the settings it asks for. Only USERID, ROOMID, and AUTH are required.

6. open up command prompt and change directory to the directory that your script is in, in windows this is the CD command, so if the script is in a folder called chillybot on your desktop on your C drive it would look something like this (CD C:\Users\username\desktop\chillybot), this will vary depending on what your path is, to find out your exact path right click on the chillybot.js file and go to properties, Location is your exact path, do not include the chillybot.js file in your CD command, it will not find it.

7. finally in order to run the bot after you have changed directory appropriately type `npm start` into command prompt and hit enter, if it does not immediately give you some kind of a runtime error it is working, login to your main turntable account and go to the room that you are running the bot in and see if it is there.

8. If everything has gone well, make your bot a moderator in the room so that it can effectively enforce its commands.

* A last note, the auto djing in this script is meant for a 5 seater room, if you have less than five seats i highly recommend you turn this feature off when you start the bot up with the /getonstage command *

If you cannot get this bot to run for some reason feel free to open an issue on github.

# Linux Bonus Instructions

## Running the bot in the background  using `screen`

If you want to run the bot in the background and be able to close the terminal:

1. create a screen named chillybot (or whever you want to name it)

`screen -S chillybot`

2. Start the bot in the screen

`npm start`

3. Disconnect from the screen by pressing `ctrl-a` and then `d`

The bot should remain running after you disconnect.

## Auto-restarting the Bot on Crash Using `Systemd`

1. Rename the provided `chillybot copy.service` to `chillybot.service`

2. Open `chillybot.service` in a text editor

3. Change the paths on line 14 (ExecStart=) to match your location of node and the location of chillybot.js. You can type `which node` in the terminal to find node's path.

4. Change the user on line 13 to be your user, NOT ROOT for security reasons

OPTIONAL: Currently the bot only restarts on crash. If you want it to restart no matter what, change the value on line 10 from `on-failure` to `always`

5. copy `chillybot.service` to `/lib/systemd/system/` filling in your path to `chillybot.service` below:

`sudo cp /path/to/chillybot.service /lib/systemd/system/chillybot.service`

6. Restart Systemd:

`sudo systemctl daemon-reload`

7. Start the chillbot servicer:

`sudo systemctl start chillybot`

8. Check that its running:

`systemctl status chillybot.service`

Optional:

9. If you want chillybot to start on system boot:

`sudo systemtl enable chillybot`
