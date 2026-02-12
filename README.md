Trying to clean up my mess a bit. This is now more status report and state of the program, which has grown enough to need explaining. The program specific docs called TerkDOC.md and consDOC.md. 

From 10000 feet, the real world consists of 1 to 8 physical sites. Each site supports one person and up to 7 AI, so every game begins with 8 players in four tribes. 

A new game starts by saving a save file:-) **TerkMake.b09** creates a galaxy, inputs your name and creates 7 AI players. The resulting file can be played alone or become the seed of a multiplayer game. **TerkAdd.b09** replaces AI players with additional sites, adding one person per site and dividing the AI load between sites. A parallel program **TerkBook.b09** maintains contact info *(chat name, hostname/IP or port/phone number)* for each site as a separate file to share between games. 

So mid-run there are 1-8 physical sites hosting a mix of real and virtual players. Communication is by token ring - a packet is passed around, every site gets every message and decides if it applies to a local player. Also included in the packet *(RSN)* are two CRCs, the map & player data wad, and the game source. 

Players are choosen in random order until all have had a go. This constitues a 'round', and it's end is a natural admin point. Default is trigger an autosave of the last completed round on each machine. Also, an Admin can use **TerkSpy.b09** to view or edit the running game *(if players accept the CRC change)*.

You might have noticed our security, which is no security at all. We learn what the last player did, and the next player's starting info, at the same time as everybody else. Replicating the last players move should reproduce the same results *(and therefore CRCs)* for everyone playing. As to those future random seeds? You won't know how to use then until the next player reports his turn. 

**TerkGame.b09** in the program orchestrating all this, and right now it's in quite the state. What we've done is completely unbalnace the game, the AI is hyperactive and all seeing, damage is all over the place. Doing many things is finding many bugs, so we rage quit bugsquashing and write new code pretty often. But work continues despite me. 

As bugs are squashed we'll normalize the aliens - this involves the recurring comment '\(* set $whatever'. 

More as it happens.
-rick

Status per module:

consAdd     - beta - safe for current save files
consBook    - alpha - creates spec addressbook
consDump    - deprecated, consSpy will replace
consGame    - alpha - just playable enough to test the networking
consMake    - beta - creates spec save file
consSpy     - alpha - edit game state as admin



