# What is this? 
**xGame** is an 'engine' for on and offline video games. Our goal is to make making the game the game. **(That's English)** like a pinball construction set. What we do is provide basic functions to let one walk through an incredibly boring game doing nothing important. Your game wad adds the interesting parts. The companion 'TerkGame' is a test wad merged in to prove the engine and debug specifics. We'll extract the game code once Terk is clean, and publish the framework for the next vict.. um author. This doc explains the engine, and the Terk manual covers one way to skin it. 

# Architecture
To work around Basic09's 64k process limit, xGame will be a collection of programs. To start:
*) xMake - create a new galaxy, the first human player, and 7 AT
*) xJoin - replace an AI player with human at remote connection (RSN)
*) xGame - ie: TerkGame. The game exec
*) xChat - text chat between players (RSN)
some debug things
*) xDump/xSpy - summarize the save file 
*) xBug  - summarize the game status (RSN)
blue sky thing
*) xShow - graphical game display (!RSN)

Because it's what I know, the first xGame code is written in Basic09. Rather than create a separate game 'wad' file, those mods are also B09, interleaved with the engine code. Easy for the game to share the engine's logic, however the programming guide will be handly. As to what our alpha program is doing:

### create galaxy
**TerkMake**, creates an initial map, the first human player, and 7 AI players. This is stored as a save file, which **TerkGame** can fire up as a single player game on one machine with no online connection. Take note, Blizethsda! Then comes **TerkJoin**, which wears two hats. To create a multiplayer game, xJoin accepts/stores a list of remote sites and contact info *(phone # or IP:port)*. This list replaces AI players in the 'current save file' and it's blasted to every site. Or, you feed it contact info for an existing game, we connect and you download that game's save file. This takes a minute, but is only done once*(ish)*. 

### Turns, players, and tribes
**TerkGame** is always an 8 player game, usually more than one 'player' per site. The sites forms a token ring network, were one site talks and everyone else follows along. The talk is play divided into 'rounds', with each player called in random order during each round. It's complicated, but should result in 8 identical map CRCs walking round the ring, proving we don't need to share the entire map again. 
Which brings up lost connections, and tribes. Players are grouped into tribes, which may include AI players. What this means is mainly up to the game wad, but there is a default action were members of a tribe flock together. If a player looses connection they replicate as an AI  who by default follows it's tribe around for protection until the real player can reconnect. 
This also brings up our first helper process, **TerkChat**. Public and private *(intratribal)* text over whatever communucations channel we are using should be easy for a CoCo. Not sure about a single board computer.

### Display
Viewing the game engine text directly, each turn begins with a summary screen consisting of an optional legend *(player and object list)*, some map views and a table of player stats. This is a fast, playable dashboard, great for debug and balancing. Or playing on a SBC. Under a windowing system, xGame thinks the thoughts while **TerkShow** runs a much better display as a separate process. 

### Being there
The game map is a grid of 64x64 cells divided into 8x8 rooms or quadrants. Each cell has two attributes, the visible 'what it is' and the invisible 'what it contains'. This includes the cell occupied by the player, so they can carry stuff. Default action simply keeps these linked and prevents 2 physical things from overlapping when moved around. Our framework is governed by three rulesets: move between rooms, move inside a room, interact with adjacent things. 

### The Player
Each player posesses 3 ability classes with similar scaling - universe wide, inside a room, inside the player. Each class is headed by the producer and main consumer of some resource. Next comes short term storage or 'stamina'. And finally, 2 consumer processes that are powered by the above. The engine provides sensible interaction, the game is allowed to break those rules. 
Using Terk as an example, the matter/antimatter class starts with a 'warp drive', which drives the ship or charges the main power source at a limited rate. That source drains to feed the pulse weapon and shields. So by default, you can't warp across the galaxy with shields up and guns blazing, at least not for long. That doesn't mean certain things can't be done. *(see kobayashi maru)*

## Create a game
xGame presents the barest outline, it's your task to fill that in. We already have more code than fits in RAM, before anything new. Don't expect one game to do it all. 

Sarting at the start, there are two menu systems that do the same thing: define a unique global command for the duration of the turn, and jump to a subroutine. First is a standard visible menu, player makes one selection that leads to another that leads to some result. There is also a trigger based menu, were a player landing on or passing by locations *(or posessions)* on the map causes inadvertantly things to happen. Like most options, these two interleave and you can't have all of both, unless your game is only about menus. 

In any case, each command or trigger is a unique number. For menus, the digits record the sequence of selections, ending at one speciofic choice. For triggers, it's the equivlent position in a command outline. All or part of this number might be used to call a specific routine, or it might be filtered through a series of routines picking at different digits. That Terk example does both. cmd 12 is engine,impulse. That starts out running the same code as cmd 11 *(engine,warp)* then does it's specific bit. Finally, all possible choices exit through a cleanup section where things like accounting for engine wear are handled. 

### Where the code goes
Back to that overlapping code. We can all share the same logic structure and save a ton of space, IF code is written to be intermingled.   

First rule, global variables can not be position or time dependant. Don't change one until that is your final answer - somebody might drop a GOSUB in the middle of your thoughts. In the same vein, don't expect a temp variable to be where you left it unless you can see it's entire lifetime on one screen. The next guy's looking no further before clobbering that thing. Despite all this, try to use something from the menu. Those are already being protected, saved, and remember, 64K.

Second rule, work with the assigned line numbers. Both menu systems use the same structure, potential modders will be looking at this  outline.

2000  Moving
2100  Interacting
2200  Looking
2300  Healing
2400  Debug
2500  Interprocess
2600  Game Menu
3000  AI 
9000  Utility Subroutines
9990  Global Data

### Where the data goes

The stock variables and display legends are stores in data statements end of program

 9990 - name of players 2-7, followed by tribe # (ABS for tribe name, - indicates AI player)
 9991 - name the 12 player stats or traits. 8 chars per name
 9992 - describe the three main categories of stats 
 9993 - objects in universe: icon:name,quantity
 9994 - name 4 to 8 tribes
 9995 - name the player's possible strategies

Configuration data is often stored as a constant inline. These are tagged '(* set something' meaning game balancing becomes 's*/(* set/' and select from the list.   

















 





 