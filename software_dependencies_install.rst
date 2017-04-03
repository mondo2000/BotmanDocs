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