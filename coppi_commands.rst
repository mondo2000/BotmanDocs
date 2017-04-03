.. _coppi_commands:

In-game Coppi Admin commands 
============================

  /mute <player name>
  /unmute <player name>
  Prevent a player using text chat or allow them to chat.
  
  /spawn horde <optional player or location name> <number of zombies>
  Spawn a horde around a player or location or at a marked coordinate.  See /set horde.
  
  /hide commands
  /show commands
  Hide commands from ingame chat which makes them all PM's or show them which makes them public.
  
  /physics on
  /physics off
  Enable or disable physics on the server.  The state of physics is persistent across reboots.
  
  /set new player/player/donor/prisoner/mod/admin/owner chat colour FFFFFF
  To disable automatic chat colouring, set it to white which is FFFFFF
  Enable or disable physics on the server.  The state of physics is persistent across reboots.
  
  /make maze
  Optional parts: wall <block name> fill <air block> width <number> length <number> height <number> x <x coord> y <y coord> z <z coord>
  Default values: wall steelBlock fill air width 20 length 20 height 3. It uses your current position for x, y and z if not given.
  Generate and build a random maze.
  It is very slow and someone must stay with it or it won't work.  Cancel it with /stop maze
  
  /stop maze
  Aborts any maze(s) that you have told the bot to create.
  
  /set/clear horde
  Marks your current position to spawn a horde ther with /spawn horde.
  Clear horde doesn't remove the horde. It only clears the saved coordinate.
  
  /add prefab <name>
  You can copy an area of blocks to later recall them or to fill the area with a block.
  This requires the latest Coppi's Additions and are not currently in Alloc's Mod.  You can give it any name but you can't reuse a name that is already defined by you.
  
  /undo
  The block commands prender, pdup and pblock allow for the last command to be undone, however since more than one person can command the bot to do block commands
  it is possible that other block commands have been done by the bot since your last block command.  If the last block command came from you, the bot will undo it.
  
  /list saves <optional player name>
  List all your saved prefabs or those of someone else.  This list is coordinate pairs of places in the world that you have marked for some block command.
  You can use a named save with the block commands.
  
  /mark <name> start
  /mark <name> end
  Mark two opposite corners of the area you wish to copy.  Move up or down between corners to add volume.
  
  /save <name>
  Now that you have marked out the area you want to copy, you can save it.
  
  /load prefab <name> at <x> <y> <z> face <0-3>
  Everything after the prefab name is optional and if not given, the stored coords and rotation will be used.
  Restore a saved prefab in place or place it somewhere else.
  If you provide coords and an optional rotation (default is 0 - north), you will make a new copy of the prefab at those coords.
  If you instead add here, it will load on your current position with optional rotation.
  If you only provide the name of the saved prefab, it will restore the prefab in place which replaces the original with the copy.
  For perfect placement, start from a south corner.
  
  /move block <name of saved prefab> here
  /move block <name of saved prefab> <x> <y> <z>
  /move block <name of saved prefab> up (or down) <number>
  Fills a saved block with air then renders it at the new position and updates the block's coordinates.
  
  /copy block <name of saved prefab> here
  /copy block <name of saved prefab> <x> <y> <z>
  Renders a saved block at your position or the coordinates you specify
  
  /rotate (or /spin) block <name of saved prefab>
  Spins a block around its first XYZ
  
  /place door block <block name or id> or prefab <name of saved prefab> named <name your door>
  Creates a special door block infront of you.
  
  /set mark <optional player>
  Temp store your current position for use in block commands which you use later. It is only stored in memory.
  If you add a player name it will record their current position instead.
  
  /set p1
  Temp store your current position for use in block commands which you use later. It is only stored in memory.
  
  /set p2
  Temp store your current position for use in block commands which you use later. It is only stored in memory.
  
  /erase <optional number> (default 5)
  Replace an area around you with air blocks.  Add a number to change the size.  Default is 5.
  
  /dig (or fill) <optional number> (default 5)
  Dig a hole or fill a hole.  Default is 5.
  This can also be used to make tunnels and walls.
  When not digging or filling up or down, a compass direction is needed (north, south, east, west)
  There are several optional parts, wide, block, tall, base and long.
  Default block is air, base is at your feet and the others default to 5.
  Examples:
  /dig north wide 3 tall 3 long 100
  /dig bedrock wide 1
  /dig up (makes a 5x5 room)
  /dig up (or room) wide 5 tall 10 (makes a 10x10 room)
  /fill east base 70 wide 2 tall 10 long 50 block steelBlock
  /fill bedrock wide 2 block 1
  
  You can repeat the last command with /again and change direction with /again west
  