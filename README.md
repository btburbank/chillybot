# Fork of chillybot

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

-----------------------------------------------------------------------------------
This bot uses the turntable api by alain gilbert which can be found here:

https://github.com/alaingilbert/Turntable-API
------------------------------------------------------------------------------------

## Instructions to Install:
1. download node.js from nodejs.org

2. download dependancys(the turntable api) by opening up command prompt and typing in `npm install` in the same directory that you will be running the script from.

3. create a new account on turntable.fm, this will be your bot. login as the bot and enter the room you want the bot in

4. get its user id and auth, and roomid and enter that into the script in the setup section
   make sure that you do this in the room that you want the bot to show up in as every room 
   has a different room id. In order to find this information out add (this bookmarklet)[http://alaingilbert.github.io/Turntable-API/bookmarklet.html] to
   your bookmark bar and use it in the room logged in as the bot 

5. open up the script (you can do this with notepad or notepad++, i recommend notepad++) and enter in the data it asks for in the setup section at the top of the script (read the instructions carefully)

6. open up command prompt and change directory to the directory that your script is in, in windows this is the CD command, so if the script is in a folder called chillybot on your desktop on your C drive it would look something like this (CD C:\Users\username\desktop\chillybot), this will vary depending on what your path is, to find out your exact path right click on the chillybot.js file and go to properties, Location is your exact path, do not include the chillybot.js file in your CD command, it will not find it.

7. finally in order to run the bot after you have changed directory appropriately type `npm start` into command prompt and hit enter, if it does not immediately give you some kind of a runtime error it is working, login to your main turntable account and go to the room that you are running the bot in and see if it is there.

8. If everything has gone well, make your bot a moderator in the room so that it can effectively enforce its commands.

* A last note, the auto djing in this script is meant for a 5 seater room, if you have less than five seats i highly recommend you turn this feature off when you start the bot up with the /getonstage command *

If you cannot get this bot to run for some reason feel free to open an issue on github.

--------------------------------------------------------------------------------------
## Running the bot in the background on Linux using `screen`

If you want to run the bot in the background and be able to close the terminal:

1. create a screen named chillybot (or whever you want to name it)

`screen -S chillybot`

2. Start the bot in the screen

`npm start`

3. Disconnect from the screen by pressing `ctrl-a` and then `d`

The bot should remain running after you disconnect.

--------------------------------------------------------------------------------------
In order to find the userid, auth and roomid of your bot use this bookmark by alain gilbert.

http://alaingilbert.github.io/Turntable-API/bookmarklet.html
--------------------------------------------------------------------------------------