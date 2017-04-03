.. _7daystodie_install:




Section 1. 7 Days to Die Server Installation
============================================




Step 1. Install 7 Days to Die Server and Mods
--------------------------------------------



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