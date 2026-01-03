# Terk, the game

 Terk? Well, it's not a copyrighted game, and it can probably be 'googled'. If you are not familar with classic Trek, the Enterprise' *(you)* runs around killing things, occasionally stopping at a starbase for repairs and resupply. We've expanded on that, Terk is an 8 player game *(seven might be AI)*, with players grouped in tribes.  
 Play begins as individuals seek other players or raw material, building strength by effort or spoils of war. Each tribe has a base where members can be rapidly restored to health. More importantly, members can join together to attack en masse *(borg out)*. Remaining individuals won't remain for long, and the game probably concludes with 'boss battles' between Triborgs.  Last Tribe standing.

Play is organized into rounds. Inside each, every player *(real or human)* is called in random order until all have played. Without knowing who's next or who's left, the only thing a body can do is take things as they come. And another thing... in turn based games, time and distance blur - warp factor 3 is both a speed and a distance covered in one turn. Shut up about the Kessel run already.

Speaking of distance, space is spacious. Looking out the window shows... nothing, usually. Instead the quadrant scan places notable surroundings in grids or 'quadrants' of 8x8 sectors. Think of a cube squashed flat and stretched such that a direct route to any system charts a straight line and distance. This isn't meant to be reality, it's a targeting screen.

# Display
Terk will run on any serial text terminal. It doesn't need display codes, not even cursor position - an Apple1 could do it. The result is a scrolling display where a 'screen' is technically the last 20ish lines, about half current stats and half a command/results scroll. There are concessions, for example there is a Legend enumerating every player, tribe, and object by full name. THat can be turned off. Also, - if you wander too far from that initial summary screen command '0' will reprint it for free.

Following the Legend (or not) is the 'Quadrant' display, using that squash things flat charting idea. The things being squashed include big things:
   * Nude stars '*' - usually something to miss or hide behind, however some 'stars' have minable antimatter. 
   * Preciv planetary system 'o' can be mined of most material classes with little fear of retaliation.
   * Civs in the suborbital  class '@' are not rigidly regulated, but tread lightly. Irritating the local MIB will most assuredly cost a money. 
   * Civs with extra-orbital capabilities 'O' are off limits without a trade agreement.  
   * 'Q' means another galaxian culture, perhaps another player's home. If you do not already know them it is probably because they hate you. Have fun with that.
And small things:
   * player initial in lower case letters, except o 
   * tribal bases as upper case letters, except O or Q

Both groups need attention. You can run into big things, while small things might chase you. 

Just right of the targeting map is an inventory of the surrounding quadrants - dumb systems, smart systems, and other players. Remember, if you can see them, they can see you. Scans *(and more)* may be exchanged. Conduct yourself accordingly.

Under that *(lower right third)* is the ship status table. There are 3 major systems, displayed as power generator/major user, storage capacity, and 2 consumer subsystems. For example, when underway 'Warp' is consumed moving the ship. Otherwise, it recharges Main Power, which pulse weapons and shields both depend on. During play all of these items are subject to wear, and of course collision or battle damage. See: Damage Control. 

You will also see a lot of the Targeting Screen. Many commands are based on the Quadrant display and request input using this simple compass rose - 8 directions and a distance or effort of 1-9. Distance is affected by the health of every system involved, while accuracy depends on  RCS health.

## Commands 
Commands can be external *(moving, shooting)* or local introspection. External facing commands end your turn, others are marked 'Not a turn' because they don't. 

### Engine:Warp 
Under best repair, warp 8 will move about 4 quadrants per turn. Chance of substantial collision damage when jumping blind. Instead, send a probe or scan out the proposed course and distance first. Next turn, the nav computer can pick an empty spot to 'land' in. 

### Engine:Impulse 
Best of times, impulse 1 moves about a sector. Note sublight propulsion requires a clear path to target, and leaving the currently mapped quadrant can yield mixed results.

### Engine:RCS
The reaction control system keeps the ship oriented and navigable. Accepts no inputs, just keep the maintenance up.

### Effector:Pulse
Aim for the 'ground zero' of a M/AM event. Mainly effective against other M/AM systems, some damage to Atomic. Do not phase your own quadrant lightly!
	
### Effector:Torpedo 
A torpedo is simply a probe with a fission warhead screwed on. It will detonate on impact*(usually)* or at a defined distance. Within a quadrant, torpedos are a most effective weapon, as they can bypass shields to physically damage any system. 
	
### Effector:Miner 
While parked next to any other system or ship, you can try to extract raw materials. These can be traded, or refined into repair materials. See: Damage Control. Mining may require a trade agreement(RSN)

### Intel:Qprobe
A Qprobe is warped into some nearby Quadrant and returns a standard scan of the area. It can detect other ships, but can not ID them or report exact location, instead a period indicates one is near. On the upside, a probe reads as space junk and doesn't lead back to you. A safe way to scout the next warp.

### Intel:Qscan
A Qscan is similar to a probe, but more invasive with visible backtrack. It reports recoverable material in or near each object as a 3 digit number estimating antimatter, atomic, and chemical stock in a range of 0-5. Warp style transport, can bu used in place of a probe, or you can scan the current quadrant by pointing back across it's center with distance 1. AI players won't care if you are scanning from a distance, nearby this might be considered a hostile act. 

### Intel:Scores
Sum of accumulated status and possesions. Not a turn.

### Intel:Legend (on/off)
Hide the player/tribe/object legend that starts each turn. Not a turn.
	
### Damage:Damage Control
Fixing things takes stuff. Our 3 major systems require three types of repair material. Engineering stores some ready to use, or refined products can be obtained from a friendly base or fellow tribesman. Or if you've mined raw materials for trade, spends a few turns to refined 'in house'.  
Along with some quantity of repair materials in stock, you have 100 units of time. Split that time into repairing or refining in six easy steps *(easy part RSN).* Requests are trimmed to match available material, and once the 100 hours are gone the computer stops asking.
The damage you'll be fixing happens to 3 major subsystems, with performance falling off at each step *(10-10-10-10 that last item is 40% down)*

#### Matter/AntiMatter 
   Directly powers the warp drive, with surplus feeding the Main Storage *(don't ask)*. The pulse energy weapons and shields are not supplied by the warp core directly, the stable supply from Main Storage is required. 

#### Fusion/Fission systems
   Fusion reactors provide sublight transport and generate fuel for the APU. Sublight torpedos, probes, and a good part of the environmental system fall under this group.

#### Reaction Control System
   Offically, the RCS is driven electrically and keeps the top side up. The same battery drives local services like plaentary mining and local food production. Less known, the RCS **supplies** that battery and can power the ship a short while without creating any kind of energy signature. Don't ask what we are spinning.

## AI opponents 
"If you don't think too well, don't think too much"- Tom Magliozzi
AI players suffer the same wear and repair concerns as humans. They are more predictable, generally following one of these sub-quests in order:
   1) If ship is damaged, fix it.
   2) If low on repair material head towards your base and restock(RSN)
   3) Chase or attack any non-tribesman visible in LR scan (3x3 quads)
   4) Join other tribesmen to form a wolfpack.
   5) Wolfpak attack opposing bases(RSN) 
   6) Cruise towards home base, looking for action

## Death
A player can die in several ways(RSN)
  1) Destroyed in combat. That's it. Everything is gone.
  2) Disabled. The ship can no longer repair itself, but can be repaired (or stolen) by others. 
  3) Wrecked.  Once the RCS spools down, she's dead, Jim. Scrap value is the minable cargo.












