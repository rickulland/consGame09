ConsTrek user manual

This initial release is basically the bones of the multiplayer version with other players reduced to 'pacman' AI - some will chase, others will run away. The manual is written assuming other humans will be allowed, but your neighbors haven't read it yet, so...

Weird stuff first. This game is organized into rounds, with every player (real or human) being called in random order until all have played. Without knowing who's next or even who's left, the only thing to do is just play. Also remember in turn based games, time and distance are the same thing. Warp factor 3 is both a speed and the distance covered in one turn. So shut up about the Kessel run already.

Speaking of distance, space is spacious. Looking out the window shows... nothing, usually. Instead notable surroundings are listed in grids or 'quadrants' of 8x8 sectors. The scale is distorted such that a direct route to every direction and 'depth' is a straight line and a distance. Imagine looking down upon an ancient naval chart, compass rose and ruler in hand.

Due to the extreme scaling, the apparent edge of the quadrant is not a line, or even a boundary. It's simply the point compression scaling gives up. Outside the galaxy center,  it's usually impossible to impulse to the next quadrant - keep that warp system working. 

As to physical display. Trek is written to run on any serial text terminal without display codes, even cursor position - an Apple1 could do it. The result is a scrolling display where a 'screen' is technically the last 20ish lines, but more on this. 
For example, the game beigns with a Legend, meaning each turn spends a few lines listing every player, tribe, and object by full name before the display proper. A few turns in the player can turn that off, leaving more of the recent action visible. Finally, if you weander too far from the following summary screen 'command 0' will reprint the last scan.

After the Legend (or not) is the primary targeting or 'Quadrant' display, using that crazy spacious space scaling idea to squash things into a flat grid. The things being squashed include big things:
   1) Nude stars '*' - usually something to miss or hide behind, however some 'stars' have minable antimatter. 
   2) Preciv planetary system 'o' can be mined with little fear of local retaliation.
   3) Civs in the 'suborbital' class '@' are not rigidly regulated, but tread lightly. Irritating the local MIB will most assuredly cost a money. 
   4) Civs with extra-orbital capabilities 'O' are off limits without a trade agreement.  
   5) 'Q' means another galaxian culture, perhaps another player's home. If you do not already know them it is probably because they hate you. This might not be a legal problem. Have fun with that.

And small things:
   6) player initial in lower case letters, except o FIXME
   7) tribal bases as upper case letters, except O FIXME

Both groups need attention for different reasons. You can accidentally run into big things 1-5, while small things 6-7 might chase you. 

Just right of the targeting map is an inventory of the surrounding quadrants - dumb systems, smart systems, and other players. Remember, if you can see them, they can see you. Scans (and more) may be exchanged. Conduct yourself accordingly.

Under the LR inventory (so lower right third) is your ship status table. There are 3 major systems. Each column begins with the power generator/major user, followed by storage capacity, and finally 2 subsystem groups using that power source. For example, when underway 'Warp' is consumed moving the ship. Otherwise, it recharges Main Power, which phasers and shields both depend on. During play all of these items are subject to wear, and of course collision or battle damage. See: Damage Control. 

You will also see a lot of the Targeting Screen. Most commands are based on the Quad display and request input using this simple compass rose - 8 directions and a distance or effort of 1-9. Accuracy of direction is affected by RCS health (qv) while distance is affected by the health of each system involved.


## Commands ##

### Engine:Warp ###
Under good repair, warp 8 will move about 4 quadrants per turn. Chance of substantial collision damage when jumping blind. Allow the nav computer to find an empty spot to 'land' in by sending a (warp powered) probe or scan out the proposed course and distance first.

### Engine:Impulse ###
Sublight speed devices (impluse,probe,torpedo) require a clear path to target. Looses 'punch' towards the edges of each quadrant, and usually can't reach the next one.

### Engine:RCS ###
The reaction control system keeps the ship oriented and navigable. Accepts no inputs, just keep the maintenance up.  

Effector:Phaser
Aim for the 'ground zero' of a M/AM event. Mainly effective against other M/AM systems, some damage to Atomic. Do not phase your own quadrant!
	
Effector:Torpedo
A torpedo is simply a probe with fission warhead screwed on. It will detonate on impact or at a defined distance. Within a quadrant, torpedos are a most effective weapon, as they can bypass shields to physically damage any system. 
	
### Effector:Miner ###
While parked next to any other system or ship, you can try to extract raw materials. These can be traded, or refined into repair material. See: Damage Control 
	Mining may require a trade agreement See: Notable objects
	
Intel:Qprobe
A Qprobe is warped into some nearby Quadrant and returns a standard targeting scan of that quadrant. Not very invasive and it can't be tracked back to you. Use qprobes to verify how well warp will work today, and let the nav computer pick an empty spot to 'land' in.

Intel:Qscan
A Qscan is similar to a probe, but more invasive with visible backtrack. What you gain is insight into recoverable material in or near each object - a 3 digit number estimating antimatter, atomic, and chemical stock in a range of 0-5.
To scan the current quadrant, aim back across the center of it with distance 1. Players nearby may consider this a hostile act, be discreet and do your scans before 'popping in.'  

Intel:Scores
Accumulated status and possesions. Not a turn.

### Intel:Legend (on/off) ###
The player/tribe/object legend start of each turn. Not a turn.
	
### Damage:Damage Control ###
Fixing things takes stuff. Our 3 major systems require three types of repair material. Engineering stores some ready to use, or refined products can be obtained from a friendly base or fellow tribesman. You ship's hold may include raw materials for trade. These can be refined 'in house' if needed.  
Along with some quantity of repair materials in stock, you have 100 units of time. Split that time into repairing or refining in six easy steps. Requests are trimmed to match available material, and once the 100 hours are gone the computer stops asking.


## Supplies and services ##

### Engine:Warp   Storage:Main ###
FTL transport and large power draw devices. Extended high factor use will reduce power available for these systems:

### Effector: Phaser ###
This energy weapon will focus to a desired source and range, then EMF bomb everything nearby. Make sure you are not nearby.

### Service: Shields ###
Protect every other system from some amount of combat or collision damage. 

### Engine:Impulse   Storage:APU ###
The fusion reactors provide sublight transport inside the targeting quadrant. In other words, aim for the space in space because running into things will hurt.  Impulse engines also power these medium draw systems. 

### Effector: Torpedo ###
Atomic weapon with subspace transport. Easily pierces force shields. Good stealth weapon, except for a penchant to crash into things.

### Service: Biological ###
You know- air, heat, and stuff. This dies, you die, everybody dies.

### Engine:RCS   Storage:Batt ###
The reaction control system draws from all other power supplies. It is not only inertial stability but the power source of last resort. Your ship and crew will live as long as this system does.

### Effector: Miner ###
Miner will try to extact raw material from any adjacent object. Initially to repair supplies, then as saleable cargo in the hold. 

### Service: Consumables ###
Replicators are sexy, but expensive and high maintenance. Sublight transport kepts the galley cookin. These operations are bundled under 'consumables'.


## Debug menu ## 
The engine does things 'Trek' players shouldn't. This debug menu is provided for debugging and balancing

### Debug:More/less info ###
on debug menu screens

### Debug:Jump X,Y ###
Drop any player at any glxX/glxY with obstacle avoidance

### Debug: Dump Galaxy ###
A chart of the physical galaxy. 'less info' shows systems & players
'more info' shows includes a summary of contents
q to bail at any point

### Debug: Dump Players ###
Many stats for each player. These should remain aligned in multiplayer games 

### Debug: Spy On ###
Shows each players turn inline, in order. With end of round marker. 

### Debug: Skip Turn ###
Just that - let everyone else go ahead while you watch. 














