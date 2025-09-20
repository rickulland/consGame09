
## temporary variables ## 
teststr2,teststr:STRING[12] - names
prnstr:STRING[80]	- line to print
tstr(3):STRING[4]	- work storage (tint,rint)
char:STRING[1]		- work character
dist,dist0,dtmp1,dtmp2:REAL - distance
tint(3),rint(3):INTEGER	- supply level 
sint(3),pint(3):INTEGER - hold contents
comp(8):INTEGER		- compare array
tmp,tmp0,tmp1,tmp2,tmp3:INTEGER - temp assignment
scanx,scany:INTEGER	- compare quadX,Y
testx,testy:INTEGER	- temp assignment X,Y
lloop,mloop:INTEGER
xloop,yloop:INTEGER
tmpX,tmpY:INTEGER	- temp use X,Y
cmd0:INTEGER		- compare cmd
pin:INTEGER		- dist input 
dmax:INTEGER		- longest allowed 
tcntY:INTEGER

## program config  ##
spaces:STRING[8]	- display string
dashes:STRING[28]	- display string
sysname:STRING[80]	- object name string
random(3):REAL		- shared random number
flags(6):BOOLEAN
flags(5) - 	1-Map Legend 
			2-Spy mode - show each players turn
			3-extended Debug Msgs 
			4-a turn? - set false, RETURN to run another command
			5-limit exceeded
			6-resc exceeded	

playR(12):STRING[8]     - resource names
tribeN(4):STRING[8]	- tribe names - must be all U.C. 
playN(8):STRING[8] 	- player names - must be all L.C. 

## global variables ##
gscan(2,64):STRING[64]	-  galaxy (1=cell contents, 2=cell meta)
                          meta=STR$(warp*100+atom*10+chem)
tscan(2,8):STRING[8]    - quad (same layers as gscan
fscan(3):STRING[32]	- 9q LRscan 

## program control ##
played(8):BOOLEAN	- played this turn?
hosted(8):BOOLEAN	- ***NOT IMPLIMENTED ***
me:INTEGER		- local player #
token:INTEGER		- current player #
glxX,glxY:REAL		- current operation's XY in galaxy
quadX,quadY:INTEGER	- quad containing above
cmd:INTEGER		- curr. command
dist:REAL 		- distance computed from player in
randl,rlmt:INTEGER	- random number
glvl:INTEGER		- 1=matl 2=resc?
play:INTEGER		- player to damage 2500
targ,targ0:INTEGER	- weapons
xstep,ystep:INTEGER

## player structure ##
playS(8,12):INTEGER	- attribute names
playM(8,3):INTEGER	- repair material - 1=M/AM 2=Atomic 3=Chemical
playX(8):INTEGER	- each player X coord
playY(8):INTEGER	- each player Y coord
playI(8):INTEGER	- player id  (trek=tribe)
playC(8):INTEGER	- cumulative score

range(8):INTEGER
target(8):INTEGER

systI(6):STRING[1]	- ***NOT IMPLIMENTED ***
syst(6):INTEGER		- galaxy create


