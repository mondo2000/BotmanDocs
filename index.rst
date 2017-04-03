Botman Installation Debian 8:
Section 1. Software installation
Step 1. Install 7 Days to Die Server and Mods
1.	Setting up a 7 Days to Die Server
a.	Download and install the 7dtd Dedicated Server in Steam Tools section, or via SteamCMD.
2.	Download and install the 7dtd Alloc Mod files 
a.	from here: http://illy.bz/fi/7dtd
3.	Download and install the Coppi MOD files 
a.	From here: https://onedrive.live.com
4.	Configure 7dtd server to allow telnet using a port and password of your choice.

Step 2. Installing Software Dependencies
1.	Main software dependencies:
a.	sudo apt-get install bless geany geany-plugin-lua mudlet ngircd xchat mysql-server phpmyadmin lua-filesystem lua-sql-mysql lua-zip lua5.1 luajit gnome-nettool openssh-server
2.	(optional) I recommend also installing xrdp and the desktop XFCE4
a.	sudo apt-get install xrdp xfce4
3.	Some other tools that are nice to have:
a.	sudo apt-get install mc, htop, putty, meld, znc.
Step 3. Installing Mudlet
Notes:
Here is an official help thread for Botman: https://7daystodie.com/forums
TheFea is working on a modified version for Smegz0r. By far the fastest and easiest way to get Mudlet running right.

Found here: https://github.com/itsTheFae/FaesMudlet2 read up on some of it

1.	Download/compile/run Mudlet:
wget https://raw.githubusercontent.com/itsTheFae/FaesMudlet2/master/setup-debian.sh
chmod +x ./setup-debian.sh && ./setup-debian.sh
wget https://raw.githubusercontent.com/itsTheFae/FaesMudlet2/master/build-mudlet.sh
chmod +x ./build-mudlet.sh && ./build-mudlet.sh

2.	Done

Step 4 - Testing Mudlet's Connections

Before you load the bot and make any configuration changes, make a quick test of the mudlet environment.
- Start Mudlet.
- Click the Help icon to test Mudlet's IRC Client is connecting to your local IRC server.
- Click the Connect icon and create a new profile to test the connection from Mudlet to your 7 days server telnet port.
If everything connected correctly you should see the 7dtd telnet output to the Mudlet window, likely asking you for the password.
You can verify the IRC client in mudlet is working by using xchat or another IRC client to watch the IRC channel (#mudlet or whichever you chose) for connection and quit lines.

Step 5 - Setting up the Bot Database

Assuming you have already installed and configured a MySQL server and PhpMyAdmin management interface, you can now create the bot databases.

The bot uses two databases which you can find in `/sql/bots.sql` and `/sql/testbot.sql`
The first database "bots" is used for storing information that many bots may use..
The second database "testbot" is the database used for individual bot data.
You will need to create a user or two users with access to these databases respectively then import/run the SQL for each.
Once done, configure the bot profile with the connection credentials. The bot depends on the databases to function correctly so editing the `bot_profile.xml` file with geany or another editor will save you time.

Step 6 - Configuring the Bot

This step is a bit of a gray area in these notes.
The one configuration required, aside from database settings in step 5, is the telnet password in the login trigger script.  Be sure to change the text sent to your server's password as set in its telnet configurations section.  This can be done while the bot is running, through mudlet, but may also save you time to do it in the bot_profile.xml file before hand.
Other configurations can be set via commands issued over IRC or in game as an admin.

Step 7 - Run and Test ALL THE THINGS!

Making sure to have your edited mudlet profile files in the mudlet-data profile directory, start mudlet and select the "newbot" (as named in the repo, otherwise named as the folder name.)  Set your telnet connection address and port and start the bot.
You should see the bot login, or attempt to.  You can verify the bot has logged in using the IRC, it will tell you.
If the bot login works you'll see it run off some initial commands to gather data about the server and any players.
From here out your bot is working.  It always needs testing, just to be sure.
In mudlet, click on the scripts icon and then click the "errors" icon to the left at the bottom of the list.
Join your 7dtd server and type `/gimme admin` (you should have already been configured as an admin in the servers config files.)
The bot will recognize you as an admin and allow you to use all the commands it has if it is working.
If anything is wrong you will see the errors in the error pane of the scripts window.
 
Step 8 - Add some port forwarding in Virtualbox.
 


Step 9 - Enjoy having a cool Bot!

Its simple really :)


