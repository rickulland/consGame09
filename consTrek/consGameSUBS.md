
## Commands ##

	2000  1)Engine
		 11)warp		1	1+4
		 12)impulse		2	2+5
	2100  2)effector
		 21)phaser		7	5+8
		 22)torpedo		8	5+8
		 23)miner		9	6+9
	2200  3)intel
	  2210   31) qprobe		8	2+8
                 32) qscan
          2220   33) player scores              1+10
          2230   34) Legend on/off 
	2300  4)damage control

	2400  5)Debug
	  2410   51) more info
	  2420   52) player XY
	  2430   53) dump galaxy
	  2440   54) dump player
          2450   55) spy on/off
          2460   56) skip turn

         2500 6)Damage
          2510   61) end turn (wear)
	  2520   62) use item (consumables)
	  2530   63) damage (hostile action)

	  9900    8) quit program

## cmd routines ##

 500 - player add - AI or network
1000 - play loop 
	1010 - setup new turn, br 3000 
        1020 - AI or SRscan prep
	1030 - long scan prep
	1050 - print term, main menu
2000 - Move
2100 - Effect
2200 - Intel
	2210 - quad scan/probe
        2211 - insert char into tscan(2,8)[8]
	2220 - player scores
	2230 - Legend on/off
2300 - Repair
2400 - Debug
	2410 - more/less info
	2420 - gotoXY
	2430 - dump galaxy
	2440 - dump players
	2450 - spy on/off
2500 - Status Updates. input: play(er), cmd0(61-63), targ0(1-12), dist0(1-64)
	2510 - 61=turn (recharge/wear)
	2520 - 62=use  
	2530 - 63=damage (user can hit multiple times)
3000 - simple AI

## helper subroutines ##

9000 - map insert - in: testx, testy, glvl, char \ mod:gscan
9001 - step right until clear - in:  \	mod: glxX,glxY
9002 - damage to other players in: glxX,glxY,pin,cmd \mod:shipS opp player
9003 - AI bounds in: tmp, tmp1 \ tmp limit >0 <65
9004 - return empty testx,testy  
9005 - return damage (set tmp=max, tmp0=ship, tmp1=start, tmp2=end)
9006 - 
9007 - return quadX, quadY from testx, testy
9008 - read  resource layer - at testx,testy set tint(1-3)
9009 - write resource layer - tint(1-3) to char
9010 - cnvt ran - in:rlmt,randl=(-1 0 +1 =seeds 1-3) out: randl=rlmt-1
9011 - print legend - 8 players, sysname
9012 - collision damage
9013 - remove player
9014 - deposit player

9100 - target vector in: cmd, glxX, glxY
9120 - 9127 ongosub

