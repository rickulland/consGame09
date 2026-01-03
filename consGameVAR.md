
## temporary variables
	each use limited to a couple screens span.
			
teststr2,teststr:STRING[12] - names
prnstr:STRING[80]	- line to print
tstr(4):STRING[4]	- work storage (tint,rint)
char:STRING[1]		- work character
dist,dist0,dtmp1,dtmp2:REAL - distance
tint(3),rint(3):INTEGER	- supply level 
sint(3),pint(3):INTEGER - hold contents
comp(8):INTEGER		- compare array
syst(6):INTEGER		- quan each system (galaxy create)

tmp,tmp0,tmp1,tmp2,tmp3:INTEGER - temp assignment
scanx,scany:INTEGER	- compare quadX,Y
testx,testy:INTEGER	- pass X,Y to gosubs
lloop,(m,x,y):INTEGER	- loops
tmpX,tmpY:INTEGER	- temp use X,Y
cmd0:INTEGER		- compare cmd
pin:INTEGER		- dist input 
dmax:INTEGER		- longest allowed 
tcntY:INTEGER

## global variables

### config
spaces:STRING[8]	- display 8 spaces
dashes:STRING[28]	- display 28 dashes
sysname:STRING[80]	- system names
random(3):REAL		- shared random numbers
flags(6):BOOLEAN 	
            1-Map Legend 
			2-Spy mode - show each players turn
			3-extended Debug Msgs 
			4-subr cost a turn? - set false 
			5-init: player density DC: raw matl ???
			6-DC: repair matl ???
playR(12):STRING[8]     - resource names
planN(5):STRING[4]      - player plan names

### program control
played(8):BOOLEAN	- played this turn?
hosted(8):INTEGER	- station hosting this player
target(8):INTEGER 	- current opponent #
leader(8):INTEGER 	- can be self
range(8):INTEGER	- distance to target()
me:INTEGER		    - local player #
token:INTEGER		- current player #
rounds:INTEGER		- rounds played
glxX,glxY:REAL		- current operation's XY in galaxy
quadX,quadY:INTEGER	- quad containing current operation
cmd:INTEGER		    - curr. command
dist,dist0:REAL		- distance computed from player in
randl,rlmt:INTEGER	- random int, range
glvl:INTEGER		- 1=object 2=contents
play:INTEGER		- player to damage bl:2500
targ,targ0:INTEGER	- weapons
xstep,ystep:INTEGER

### map and player data
gscan(2,64):STRING[64]	-  galaxy (1=cell contents, 2=cell meta)
                              meta=STR$(warp*100+atom*10+chem)
tscan(2,8):STRING[8]    - one 8x8 quad (same layers as gscan)
fscan(3):STRING[32]	- 9 quad inventory

### player, tribe 
tribeN(4):STRING[8]	- tribe names - must start U.C. 
tribeX(4):INTEGER       - tribe base X
tribeY(4):INTEGER       - tribe base y

playN(8):STRING[8] 	- player names - must be all L.C.
playS(8,12):INTEGER	- attribute quantities
playR(12):INTEGER	- attribute names

playX(8):INTEGER	- player X coord
playY(8):INTEGER	- player Y coord
playI(8):INTEGER	- player id  (tribe)
playM(8,3):INTEGER	- repair matl in 3 classes
playC(8):INTEGER	- cumulative score
playP(8):INTEGER	- players plan
		3000	1) open (DC then opp scan)
		3010	2) chase/follow
		3010	3) leader also tow tribesmen
        3030    4) tribemen shoot every target
		3040	5) return to base for repair

 9990 DATA - 8(s8,i1) playername, id (tribe#). player names all LC
 9991 DATA - 12(s8) trait (subsystem) names
 9992 DATA - 1(s~46) healing (damage control)
 9993 DATA - 6(s8,i3) objects(system) names, quantities
 9994 DATA - 4(s8) Id (tribe) names - tribe start UC
 9995 DATA - 5(s4) Player plan names 
































































