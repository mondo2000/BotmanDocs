.. _admin_commands:



In game Admin commands
======================


 /activatetp <teleport>
Change a teleport to active.  It will now be able to teleport some or all players depending on...

 /add reset zone
Tell the bot that the region you are in is a reset zone.  It will alert players as they enter and...

 /admin add <playername> *
Add a player to the admins table.  The slash is required.

 /admin remove <playername> *
Remove a player from the admins table.  The slash is required.

 /arrest <playername>
Send the player to the prison location.  A location called prison must exist.  The player will be...

 /baditem <item> / baditemadd <item>
Add an inventory item to the banned items table.  The name must be identical to the name used to...

 /baditemdrop <item> / baditemdel <item> / baditemrem <item>
Remove an item from the banned items table.

 /baditems
List all the items that are not allowed in player inventories

 /bases nearby <optional number in meters>
List all the player bases near you.  This works like the who command and defaults to 200 meters....

 /cancel reboot
Cancel a scheduled reboot.  Will not work if a reboot was created with the forced flag.

 /closeto <playername>
Teleport 10 meters below and off to the side of a player.  Do this while flying as you will be...

 /closetp <teleport name>
Complete  a teleport called <teleport name>.  This will activate it and you will be...

 /crimescene <playername>
Teleport to the where a player was when they were arrested.  Very useful for investigating a PVP...

 /deactivatetp <teleport>
Stop a teleport from activating.

 /fetch <playername>
Teleport a player to you.  If the player has not done enabletp or is another admin, you cannot...

 /gimme gimme
Gimme messages are sent to in-game chat for everyone to read

 /gimme off
Disable gimme so nobody can use it.

 /gimme on
Enable gimme so it can be played.

 /gimme peace
Most gimme messages will be private messages to the player.  Only a few select prizes are still...

 /gimme reset
Resets everyone’s gimme counter allowing them to play 10 gimme games.  The gimme game is...

 /goto <playername>
Teleport to a player.  Also works for offline players if the bot has seen them.

 /hotspot <message>
Add a hotspot (private message) at your location.  You can optionally set a size.  Just include a...

 /hotspot delete
Delete the nearest hotspot.  Use the hotspots command to find the nearest hotspot.

 /hotspots <optional number>
List all the hotspots near you.  The default is to list hotspots within 20 meters of you.  Add a...

 /ignore player <playername>
Tells the bot to allow a specific player to have banned items in their inventory (except bedrock).

 /ignoreadmins (also exclude admins)
Tells the bot not to include admins in tests for banned inventory or to block admins from...

 /include player <playername>
The player will no longer be allowed to have banned items in inventory.

 /includeadmins (or include admins)
Tells the to include admins in tests for banned inventory and to block admins from entering areas...

 /just release <playername>
You can release a prisoner without returning them.  They will have to find their own way home.

 /killtp <teleport>
Delete a teleport.

 /list reset zones
Display the list of reset zones.

 /lobby <playername>
If a location called lobby exists, you can send a player to it.  If the player is offline, they...

 /location add <location name>
Add a location.

 /location disable <location name>
Change the status of a location to disabled.  

 /location enable <location name>
Change the status of a location to enabled.

 /location private <location name>
Change the status of a location to private.

 /location public <location name>
Change the status of a location to public.

 /location remove <location name>
Delete a location.

 /lock <playername> *
Server owners can lock a player in prison.  Only a server owner will be able to release that...

 /map size <number>
Set the size of the map (in meters) from 0,0 in which players are allowed to explore.  If they...

 /opentp <teleport name>
Create a teleport called <teleport name>

 /owntp <teleport> <playername>
Teleports are owned by their creator.  Use this command to change ownership to another player....

 /pause reboot
Suspend a pending reboot.

 /playerhome <playername> (or playerhome2). Alias playerbase/playerbase2
Teleport to the location of a player’s base teleport or base2 teleport.  

 /prison size <number>
Set the size (in meters) of the prison.  Prisoners will be prevented from exploring beyond this...

 /prisoner <playername> <reason for being a prisoner>
You can enter a reason for arresting a player.  Currently this isn’t reported anywhere but I will...

 /prisoners
List all the prisoners

 /privatetp <teleport>
Change a teleport to private.  Only admins, the teleports owner and their friends can use it

 /protect <playername>
Enables base protection on a players first base.  To protect a second base the command is...

 /publictp <teleport>
Make a teleport public.  Anyone can use it.

 /reboot *
optional parameters: when idle/empty (admins can do this version) n minutes/hours (restricted...

 /release <playername>
Release a player from prison and return them to where they were arrested.  If the prisoner killed...

 /remove donor <playername>
Remove a player from the donors table.

 /remove reset zone
If the region you are in is a reset zone, this will remove it from the list and players will no...

 /rescue <playername>
An alternate form of the fetch command but ignores enabletp.  For use with uncooperative players.

 /reset gimmehell
The gimmehell game uses its own spawn queue which is loaded at the beginning of a game.  If you...

 /resettimers <playername>
This will reset the base cooldown (30 minute) timer and the gimme count for an individual player.

 /return <playername>
You can return a player to wherever they were teleported from.  Players can use it on themselves...

 /send <playername> to <playername>
Teleport a player to another player even if the other player is offline.

 /sendhome <playername>
If a player has set a base you can send them to it.  Use sendhome2 <playername> to send...

 /set base size <size> <playername>
By default base protection is 32 meters from the base teleport which makes a total of 64 meters...

 /setbase <playername>
Set a base teleport where you are standing for a player.  No setbase2 version yet.

 /setexitbase <playername> (or setexitbase2 <playername>)
Set the exit point for the players base or base2 teleport.  You only need to use this command...

 /teleports (optional <playername>)
List all the teleports.  If the list gets too long add a playername to just see teleports created...

 /timeout <playername>
Send a player to timeout (2km above a lake).  They will free-fall until they are below 500...

 /tp <teleport name>
Teleport to the location of a teleport.  You will immediately be teleported by it so either step...

 /track <playername>
You will teleport to each of the last 30 steps a player took so you can see where they went....

 /unpause reboot
Resume a paused reboot.

 /unprotect <playername>
Disable base protection.  Use unprotect2 to do this to a player’s second base if they have one.

 add donor <playername>
Add a player to the donors table.