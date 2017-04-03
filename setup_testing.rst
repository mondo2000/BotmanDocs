.. _setup_testing:

Section 5. Setup and Testing
============================

Step 1. Setting up ngircd, bot channels
---------------------------------------
  The default install should work. Bot may say no such user or channel.
  
  More to come on this.

..
 ToDo: detailed steps need to clarify with Smegz0r about static channels
..

 **Step 2. Testing Mudlet's Connections**
 
  Before you load the bot and make any configuration changes, make a quick test of the mudlet environment.
 - Start Mudlet.
 - Click the Help icon to test Mudlet's IRC Client is connecting to your local IRC server.

   You should see something like this:

   | Capabilities acknowledged: multi-prefix
   | Welcome to the Internet Relay Network !~mudlet@localhost
   | Your host is some.site.com, running version ngircd-22 (x86_64/pc/linux-gnu)

 - Click the Connect icon and create a new profile to test the connection from Mudlet to your 7 days server telnet port.

   | In the Server address block put: 0.0.0.0
   | In the Port blockput: 8081
   | or your own IP:Port numbers if you have different ports

  **If** everything connected correctly you should see:

    | [  OK  ]  - Lua module rex_pcre loaded.
    | [  OK  ]  - Lua module zip loaded.
    | [  OK  ]  - Lua module lfs loaded
    | [  OK  ]  - Lua module sqlite3 loaded
    | [  OK  ]  - Mudlet-lua API & Geyser Layout manager loaded.
    | [ INFO ]  - Looking up the IP address of server:127.0.0.1:8081 ...
    | [ INFO ]  - The IP address of 127.0.0.1 has been found. It is: 127.0.0.1
    | [ INFO ]  - Trying to connect to 127.0.0.1:8081 ...
    | [ INFO ]  - A connection has been established successfully.

    | Please enter password:
    | YourTelnetPassword
    | Logon successful.

    | \*** Connected with 7DTD server.
    | \*** Server version: Alpha 15.2 (b8) Compatibility Version: Alpha 15.2
    | \*** Dedicated server only build

    | Server IP:   Any
    | Server port: 26900
    | Max players: 10
    | Game mode:   GameModeSurvivalMP
    | World:       Random Gen
    | Game name:   BotLovU
    | Difficulty:  3

  You can verify the IRC client in mudlet is working by using xchat or another IRC client to watch the IRC channel (#mudlet or whichever you chose) for connection and quit lines.

 **Step 3. Setting up the Bot Database**

  The bot uses two databases which you can find in ``USERNAME/mudlet-data/profiles/newbot/sql``: `bots.sql` and `testbot(structure only).sql`

  The third sql is starting data for your bot(s): `testbot(sample data).sql`
  
  The first database "bots" is used for storing information that many bots may use.
  
  The second database "testbot" is the database used for individual bot(s) data.
  
  Quick and easy Sql import.
  
  | ``sudo mysql -u USERNAME -p PASSWORD bots < USERNAME/mudlet-data/profiles/newbot/sql/bots.sql``

  | ``sudo mysql -u USERNAME -p PASSWORD testbot < USERNAME/mudlet-data/profiles/newbot/sql/testbot(structure only).sql``

  | ``sudo mysql -u USERNAME -p PASSWORD testbot < USERNAME/mudlet-data/profiles/newbot/sql/testbot(sample data).sql``

   Or

  Assuming you have already configured a MySQL server and PhpMyAdmin management interface, you can now use PhpMyAdmin to create the bot(s) databases.

   
  You will need to create a user or more with access to these databases respectively then import/run the SQL for each.
  
  Once done, configure the bot profile with the connection credentials. The bot depends on the databases to function correctly so  editing the ``USERNAME/mudlet-data/profiles/newbot/scripts/editme.lua`` file with geany or another editor (nano) will save you time.

  ``nano USERNAME/mudlet-data/profiles/newbot/scripts/editme.lua``

 **Step 4. Configuring the Bot**

   The one configuration required, aside from database settings in step 6, is the telnet password in the login trigger script.  Be sure to change the text sent to your server's password as set in its telnet configurations section.  This can be done while the bot is running, through mudlet, but may also save you time to do it in the `scripts/editme.lua` file beforehand.

   Other configurations can be set via commands issued over IRC or in game as an admin.

  ``nano USERNAME/mudlet-data/profiles/newbot/scripts/editme.lua``

 **Step 5. Run a Test**

  Making sure to have your edited mudlet profile files in ``USERNAME/mudlet-data/profiles/newbot/current/bot_profile.xml`` the mudlet-data profile directory, start mudlet and select the "newbot" (as named in the repo, otherwise named as the folder name.)  Set your telnet connection address and port and start the bot.

  You should see the bot login, or attempt to.
  You can verify the bot has logged in using the IRC, it will tell you. If the bot login works you'll see it run off some initial commands to gather data about the server and any players.
  From here out your bot is working.  It always needs testing, just to be sure.
  In mudlet, click on the scripts icon and then click the "errors" icon to the left at the bottom of the list.
  Join your 7dtd server and type `/gimme admin` (you should have already been configured as an admin in the servers config files.)
  The bot will recognize you as an admin and allow you to use all the commands it has if it is working.
  If anything is wrong you will see the errors in the error pane of the scripts window.

 **Step 6. Enjoy having a cool Bot!**