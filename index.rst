=================================
**Botman Installation Debian 8:**
=================================

***************************************
**Section 1. 7 Days to Die Server Installation**
***************************************

 **Step 1. Install 7 Days to Die Server and Mods**

  1. Ensure you're using the most up to date packages:
    
     ``sudo apt-get update``
    
     ``sudo apt-get upgrade``
    
     ``sudo apt-get dist-upgrade``
    
     ``sudo reboot``

  2. Setting up a 7 Days to Die Server using `LGSM <https://gameservermanagers.com/lgsm/sdtdserver/>`_

   a. To find out what xx-bit you are running
    ``cat /proc/version``

      i.e.

    ``Linux version 3.16.0-4-amd64 (debian-kernel@lists.debian.org) (gcc version 4.8.4 (Debian 4.8.4-1) ) #1 SMP Debian  3.16.39-1+deb8u2 (2017-03-07)``

    I would install the 64-bit

   b. Install one or the other bases on what xx-bit version of Debian you have
     | For Debian 64-bit
     ``sudo dpkg --add-architecture i386; sudo apt-get install mailutils postfix curl git wget file bzip2 gzip unzip bsdmainutils python util-linux tmux lib32gcc1 libstdc++6 libstdc++6:i386 telnet expect``

     | For Debian 32-bit
     ``sudo apt-get install mailutils postfix curl git wget file bzip2 gzip unzip bsdmainutils python util-linux tmux libstdc++6 telnet expect``
   c. Create a user and login.

    ``sudo adduser sdtdserver``

    ``passwd sdtdserver``

    ``su - sdtdserver``

   d. Download the script.

    ``wget https://gameservermanagers.com/dl/sdtdserver``

   e. Make it executable.

    ``chmod +x sdtdserver``

   f. Add Steam login details.

    | You will need to enter a Steam username and password to download 7 Days to Die dedicated server.
    | It is recommended that you create a new Steam username just for the server.

    ``nano sdtdserver``

    | # Steam login
    | steamuser="username"
    | steampass="password"
   
   g. Run the installer and follow the instructions.

    ``./sdtdserver install``
..
 ToDO: need to work commands for below to download/unpack
..
  
   3. Download and install the 7dtd Alloc Mod files
    a. From here: `http://illy.bz <http://illy.bz/fi/7dtd/server_fixes.tar.gz>`_
   4. Download and install the Coppi Mod files 
    a. From here: `https://1drv.ms <https://1drv.ms/f/s!AkVY2tzB9dkMhq1paa_Wmp_h8rY62g>`_
   5. Configure 7dtd server to allow telnet using a port and password of your choice.
    ``nano /opt/sdtdserver/serverfiles/sdtd-server.xml``

    | ``<property name="TelnetEnabled"                        value="true"/>``
    | ``<property name="TelnetPort"                           value="8081"/>``
    | ``<property name="TelnetPassword"                       value="pasw0rd1"/>`` 
    Note: Don't use this password please change it to your own
   6. Test telnet

    ``telnet localhost 8081``

    You should see something like this:

    | Trying ::1...
    | Trying 127.0.0.1...
    | Connected to localhost.
    | Escape character is '^]'.
    | Please enter password:
    | \********
    | Logon successful.
    | \*** Connected with 7DTD server.
    | \*** Server version: Alpha 15.2 (b8) Compatibility Version: Alpha 15.2
    | \*** Dedicated server only build

***************************************
**Section 2. Software Installation**
***************************************

 **Step 1. Installing Software Dependencies**

  1. Ensure some essential system utilities are installed

   ``sudo apt-get install software-properties-common python-software-properties``

  2. Bot main software dependencies:

   ``sudo apt-get install bless geany geany-plugin-lua mudlet ngircd xchat phpmyadmin lua-filesystem lua-sql-mysql lua-zip lua5.1 luajit gnome-nettool openssh-server``

  4. There are a few flavors of MySQL you can install. I recommend MariaDB. Remember this password you will need it.  
    
    Oracle MySQL
    
    ``sudo apt-get install mysql-server mysql-client libmysqlclient-dev``
        
    MariaDB
    
    ``sudo apt-get install mariadb-server mariadb-client libmysqlclient-dev``
        
    Percona
        
    ``sudo apt-get install percona-server-server-5.6``

  5. **(optional)** I recommend also installing xrdp and the desktop XFCE4 (you will need a desktop GUI) 

     ``sudo apt-get install xrdp xfce4``
  
  6. **(optional)** Some other tools that are nice to have:

   ``sudo apt-get install mc, htop, putty, meld, znc``
***************************************
**Section 3. Setting up the bot database(s)**
***************************************

 **Step 1. MySQL database/user ceation**

  1. Create MySQL database(s)/user(s) for the bot
     
   a. Start mysql client: see step 4 for password    
    
     ``sudo mysql -uUSER -pPASSWORD``

       i.e.

     ``sudo mysql -uroot -pmysql411``

   b. Create the bot database(s)

     ``CREATE DATABASE bot;``

     ``CREATE DATABASE testbot;``

   
   c. Create users for the bot database(s)
    
    ``GRANT ALL ON SomeDatabaseName.* TO 'SomeUserName'@'SomeHostName' IDENTIFIED BY 'SomePassword';``
        
        i.e.
        
    ``GRANT ALL ON bots.* TO 'bots'@'localhost' IDENTIFIED BY 'bots411';``

    ``GRANT ALL ON testbot.* TO 'testbot'@'localhost' IDENTIFIED BY 'bots411';``

   d. Grant extra user permissions
    
    This adds needed permissions to the account you just created.
    
    ``GRANT FILE ON *.* TO 'SomeUserName'@'SomeHostName';``
        
        i.e.
    
    ``GRANT FILE ON *.* TO 'bots'@'localhost';``

    ``GRANT FILE ON *.* TO 'testbot'@'localhost';``

   e. Close the mysql session 

     ``exit``

***************************************
**Section 4. Installing/Setting up Mudlet**
***************************************

 **Step 1. Installing Mudlet**

  Notes:

  Here is an official help thread for Botman: `https://7daystodie.com/forums <https://7daystodie.com/forums/showthread.php?52933-Botman-server-manager-official-support-thread>`_


  TheFea is working on a modified version for Smegz0r. By far the fastest and easiest way to get Mudlet running right.

  Found here: `https://github.com/itsTheFae/FaesMudlet2 <https://github.com/itsTheFae/FaesMudlet2>`_ read up on it

  1. Download/compile/run Mudlet:
   ``wget https://raw.githubusercontent.com/itsTheFae/FaesMudlet2/master/setup-debian.sh``

   ``chmod +x ./setup-debian.sh && ./setup-debian.sh``

   ``wget https://raw.githubusercontent.com/itsTheFae/FaesMudlet2/master/build-mudlet.sh``

  Note: This last step will take some time to build

   ``chmod +x ./build-mudlet.sh && ./build-mudlet.sh``

  2. Download/Clone Botman 

  Found here: https://bitbucket.org/mhdwyer/botman

..
 ToDo: git, clone, copy
..

***************************************
**Section 5. Setup and Testing**
***************************************

 **Step 1. Setting up ngircd, bot channels**

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
***************************************
**Section 6. Thanks**
***************************************
| Smegz0r
| TheFea
| Alloc
| Coppi
