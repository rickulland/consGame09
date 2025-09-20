consGame will be an engine for on and offline video games. It provides a map and default functions that let one walk through an incredibly boring game doing nothing important. Actions descibed as 'default' become the base interface for your game wad, which you can ignore to add interesting parts  in manageable chunks. 

That code isn't available yet. Instead 'consTrek' is both the engine code and test wad. So it serves two masters and is not especially good at either task. It actually runs, so we can exersize ideas using a default display. And it actually crashes, go we're getting bugs squashed. 

Plus it's easier to describe specifics than explore possibilities. So read Treks manual before you read this one first.

Once it's debugged, we'll rip out all the Trek stuff and release a proper engine.

## Missing ##
Shared source is easy to fake. We are thinking security by comm program. This open code should connect to a black box. That box computes both it's CRC and ours, sending both along with the user data. Security and version checking.

## Players & Tribes ##
This is always an 8 player game, which begins with one machine launching a single player, 7 AI instance. This generates an initial token number, 3 random 'seeds', and a CRC or checksum of the newly created map.  Trek operates at this level.

Each player is a member of a tribe. By default members of a tribe are nice to each other (will trade, wont kill) but YMMV. Each tribe has a home base where by default members are quickly restored to health and other perks. 

A new player joins the game by taking over one of the AI (and it's tribe) while downloading the current map. Combined that is pushing 10K and can be a little time consuming over a modem, but it's only needed once. Once on our token ring network, we all compare notes and have a great time until a player looses connection. When that happens their status reverts to AI, preserving all goodies (minus a small fee) for their return.

## Communication ##

Play is divided into 'rounds', inside each players are called in random order. The player named by token executes a turn, which passes those commands plus the standard packet (resulting map CRC, next token, 3 randoms) to the comm software which adds 'missing' (see above) and this is shared with the group.   You've probably surmised this is client to client 

## Display ##
Default is a summary screen including an optional legend (player and object list), a few map views and a table of player stats. Use this dashboard to make gameplay 'fun'. And then change it.

Working on alternate data screens like remote and extended views. Trek will include examples of each. Also in the fire are 'widgets' for example data bars vs. the current list of numbers. 

## Map ##
The game map consists of a grid of 64x64 cells divided into 8x8 rooms. Each cell has two attributes, the visible 'what it is' and the invisible 'what it contains'. Default action simply keeps these linked and moving around without overlap.

## Moving/Doing ##
There are three rulesets covering three ranges. Move between rooms, move inside a room, interact with self (and adjacent things). Trek simply renames the defaults, no need to repeat here.

## Being ##
Each player has 3 trait classes with similar scaling - against world, against room, against self. The default chart shows an upper row as the producer and main consumer of some resource. The next row describes short term storage or 'stamina'. And finally, 2 subprocesses that are powered by the above. All are subject to their own damage, it can really add up for the last system in line.
  
## Recovery ##
The three trait classes are restored from inner reserves. This can happen over time, or be helped along with player effort, like spending a turn in Trek's 'Damage Control' screen. 

## Taking/Trading things ##
As your inner stores deplete, turn to the resource layer. The three classes of tradable items match up with the three traits (funny that). Mined or traded material is carried by the player and is sometimes visible to others. 

Default allows converting that 'raw' material into inner reserve by eating or whatever. To get raw material, simply take things from adjacent cells that are not occupied, or trade with other players in your tribe. 


## Future ##

The data exchangge bit is being built separately. The player data to be contained in one TYPE for easy moving in Basic09... more as it happens -rick


