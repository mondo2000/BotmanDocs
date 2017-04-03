.. _database_setup:


Section 3. Setting up the bot database(s)
=========================================

Step 1. MySQL database/user creation
------------------------------------

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
