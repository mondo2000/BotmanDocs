.. _ngircd_setup:

Section 4. Setting up ngIRCd
============================

Step 1. Editing ngIRCd.conf
---------------------------


New change to botman:
^^^^^^^^^^^^^^^^^^^^^
  1. You will want to set static channels for your bots.

   a. This can be done by editing /etc/ngircd/ngircd.conf use nano or your editor of choice.

     ``nano /etc/ngircd/ngircd.conf``

       scroll down until you see

     | [Server]
     |        # More [Server] sections, if you like ...``


 
  2. Copy and past the following into ngircd.conf right below the above

    
             | [Channel]
             |        Name = #bot1
             |
             |        # Topic for this channel
             |        Topic = Bot alerts channel
             |
             |        # Initial channel modes
             |        ;Modes = tnk
             |
             |        # initial channel password (mode k)
             |        ;Key = Secret
             |
             |        # Key file, syntax for each line: "<user>:<nick>:<key>".
             |        # Default: none.
             |        ;KeyFile = /etc/ngircd/#chan.key
             |
             |        # maximum users per channel (mode l)
             |        ;MaxUsers = 23
             |
             | [Channel]
             |        # Name of the channel
             |        Name = #bot2
             |
             |        # Topic for this channel
             |        Topic = Bot alerts channel
             |
             |        # Initial channel modes
             |        ;Modes = tnk
             |
             |        # initial channel password (mode k)
             |        ;Key = Secret
             |
             |        # Key file, syntax for each line: "<user>:<nick>:<key>".
             |        # Default: none.
             |        ;KeyFile = /etc/ngircd/#chan.key
             |
             |        # maximum users per channel (mode l)
             |        ;MaxUsers = 23
             |
             | [Channel]
             |        # Name of the channel
             |        Name = #new_alerts
             |
             |        # Topic for this channel
             |        Topic = Bot tracker channel
             |
             |        # Initial channel modes
             |        ;Modes = tnk
             |
             |        # initial channel password (mode k)
             |        ;Key = Secret
             |
             |        # Key file, syntax for each line: "<user>:<nick>:<key>".
             |        # Default: none.
             |        ;KeyFile = /etc/ngircd/#chan.key
             |
             |        # maximum users per channel (mode l)
             |       ;MaxUsers = 23
             |
             | [Channel]
             |        # Name of the channel
             |        Name = #new_watch
             |
             |        # Topic for this channel
             |        Topic = Bot watch channel
             |
             |        # Initial channel modes
             |        ;Modes = tnk
             |
             |        # initial channel password (mode k)
             |        ;Key = Secret
             |
             |        # Key file, syntax for each line: "<user>:<nick>:<key>".
             |        # Default: none.
             |        ;KeyFile = /etc/ngircd/#chan.key
             |
             |        # maximum users per channel (mode l)
             |        ;MaxUsers = 23
             |
             | [Channel]
             |        # Name of the channel
             |        Name = #new_watch_wat
             |
             |        # Topic for this channel
             |        Topic = Bot watch channel
             |
             |        # Initial channel modes
             |        ;Modes = tnk
             |
             |        # initial channel password (mode k)
             |        ;Key = Secret
             |
             |        # Key file, syntax for each line: "<user>:<nick>:<key>".
             |        # Default: none.
             |        ;KeyFile = /etc/ngircd/#chan.key
             |
             |        # maximum users per channel (mode l)
             |        ;MaxUsers = 23
             |
             | [Channel]
             |        # Name of the channel
             |        Name = #new_tracker
             |
             |        # Topic for this channel
             |        Topic = Bot tracker channel
             |
             |        # Initial channel modes
             |        ;Modes = tnk
             |
             |        # initial channel password (mode k)
             |        ;Key = Secret
             |
             |        # Key file, syntax for each line: "<user>:<nick>:<key>".
             |        # Default: none.
             |        ;KeyFile = /etc/ngircd/#chan.key
             |
             |        # maximum users per channel (mode l)
             |        ;MaxUsers = 23 

|

  4. crtl + X

  |

  5. Y

  |

  6. enter 

  |

  7. sudo service ngircd stop

  |

  8. sudo service ngircd start

  |

  9. sudo service ngircd status

  |

  10. done!