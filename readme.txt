
Title    	: ClanRing CRCTF v3.5
Filename 	: crctf35.zip
Version  	: 3.5
Date     	: 02/01/2011
Authors  	: R00k
Email    	: quakehead@gmail.com
URL      	: www.quakeone.com/crctf
Description	: Competition Capture The Flag (CTF) mod for Quake I (Netquake).
		  Based on works by Dave 'Zoid' Kirsch, Paul Baker, and JP Grossman. 
		  ProQuake Compatible. Compiled with Frikqcc v2.5
____________________________________________________________________________

New Features
____________________________________________________________________________

v3.5

+ Added fastarts as a voteable option.

+ Fixed: Optimized the ban routines.

+ Added: Death Match Mode 4. Weapons and Ammo respawn times are 15 seconds, and if a player already has a weapon, they cannot retake.

+ Changed: Smoother 'tournament' camera angle interpolation.

+ Added : Break away hook. The hook breaks if the difference of velocity of the two players hooked together is greater 640.

+ Added : Proquake's PQ_TEAMSCORES command to show teamscores in statusbar.

+ Added	: tossruneoff command for crctf.cfg, disables rune tossing (impulse 19), runetoss is on by default.

+ Added	: dischargeoff/dischargeon commands to crctf.cfg Default is dischargeoff.
	dischargeoff: 	turns OFF lightning gun discharging in practice mode. 
			Limits discharging to affect only players in liquid, not out of water, for match mode and normal mode.
			Also biosuit protects 80% from discharging. (Think of it as a temporary "Red Armor" for underwater only)
	
	dischargeon: 	uses normal discharging rules.	
	
	Can also toggle via admin options no spooge.
	
+ Fixed: hook select is 1/2 time weapon select.

+ Added: Proquake's pqc_ values to pass matchtime and teamscores from CRCTF to a proquake's Client.
	This properly shows to all clients the true pq_timer values especially to clients
	who connect after the match has started. Also updates the pq_teamscores properly.
	
+ fixed: Automatic request to unpause the match when it is not paused.

+ Changed: In classic mode, apon connecting you are automatically put on a team.

+ fixed: Players connecting during intermission didnt get aliases bound properly.

+ fixed: If player lost flag in prematch, the statusbar still showed flag icon.

+ modified: REGEN & MEGAHEALTH CHANGE
	Megahealth respawns normally 20 seconds after the player's health drops back down to 100 or less.
	Regen will prolong this respawn time to the extent that megahealth is no longer effective, for gameplay.
	So, if a player with regen gets megahealth, and their health hasn't dropped below 100 for over 105 seconds,
	(same as 5 second pause + 100 health points [default time]), then it respawns 20 seconds afterwards.
	Logically, if a player took megahealth without regen and just stood there without getting shot, 
	it would take 105 seconds for megahealth to wear off.	

+ fixed: Proper handling of doors, plats, and trains during match paused, and unpausing. 

+ changed: Sethook now is used to control the pullspeed of the hook: slow (800), fast (1000 default), or 
	   diasble the hook all together.

+ changed: Death sounds are no longer GLOBAL, instead when a player dies, its only heard, in proximity.
	   This is good in a few ways. 
	   1.) Easier on the ears while playing 
	   2.) You dont actually know when your teammates dies, unless you read the obits
	   3.) If someone dies nearby, you now can hear in what direction, 
	   	ie. you heard death, read obit, know who/where death occured...

+ added: Flags are reset at the t-minus 10 countdown in match mode, and cannot be touched until match start.

+ fixed: Reduced occurance of respawning at the origin of death.

+ fixed: allow players to connect during an intermission.

+ added: display message to show proquake versions of a client on connection.
	(unknown, if using pre 2.0 or NON proquake if using anything else)
		
+ added: flags to .ent files

+ fixed: damage momentum from blast radius 	 

+ fixed: Observers cannot change to team colors while a match is in progress, *if* the match is LOCKED.
	 This deters "coaching" by using mm2 and chasecam to talk to players.
	 
+ fixed: Bug where prematch flag runs, would allow a player to type NOTREADY while holding the flag,
	 and then change teams. Thus, the player still had the flag, even in observer mode. After match
	 start, flag would fall on map and not respawn at base.

+ fixed: AUTOCHASE's "DEADCAM" SHAKE bug. 

+ added command to toggle auto teammate identifier, AUTOID
	Identifies when crosshair passes over teammate:	[name][health/armor]

+ disabled exploit that allowed observers to toss items while eyecamming/chasecamming (OOPS!)

+ no weapon dropping during paused match

+ fixed autochase bug (from 3.19j)

+ added bancode

+ fixed flags during match pause.

+ hook and runes are paused properly.

+ if match is aborted the timelimit is reset to the value the match started at.

+ fixed (.frags) assignment to world entity bug 
	server crash when someone connected at the same time a team had captured the flag.	
	
+ Fixed Observer's "up by" score.
	was not accounting for CTF score only kill frags.

+ If a flag falls on a trigger_hurt, it automatically returns to base.(requested)
+ ignored levels.cfg in match mode (quicker map loads)

+ Fixed flaw in vote disable rune code. 
	Rune entites were not removed only "disabled" (ie. no model, no touch, no respawn)
	When the vote to re-enable runes while on same map, it would create NEW entities.
	Now, disabled runes are truely removed.

+ Fixed Platfroms during paused match.

+ Fixed AutoStats to log files. Use cfg command AUTOSTATSON 
	All death messages are logged.
	CTF announcements are logged.

+ Observers cannot initiate votes during match.

+ Player's cannot suicide during a paused match.

+ Flags and runes are truely paused during match pause
 
+ Anticrossdressing code implemented. CUSTOM SHIRT COLORS ARE AVAILABLE!
  Though, you cannot xdress! This means, YES you can have (color 0, 13), or
  (color 5, 4) ETC... But NOT color (2, 4) OR (13, 4) OR (4 , 13)...

+ Increased delay before hook returns after player lets off fire button if 
  hook has not touched anything. (was 0.3 seconds, now its 1/2 a second)

+ No damage during paused matches.

+ Flag Carrier has primary time slice for AutoCam.

+ Voter's name added to vote request message, also to yes/no votes.

+ Added the centerprint StatusBar from P.baker's crctf 2.8.

+ Hook damage normalized for all ticrates.
	At lower ticrate values, ie (0.05) damage encured was updated faster.

+ Added DYNAMICHOOKON and DYNAMICHOOKOFF commands.	
	Dynamic hook simulates the hook physics of 0.1 ticrate for all ticrates,
	off = ticrate determines hook physics (DEFAULT).
	**** This is used to actually limit the bunny-hopping speed, when landing from a hook. 
	Bunny-hop speed is limited to 576.
	
+ Fixed hooking in windtunnels, works at all ticrates.		

+ Support for fraglimit in matchmode.
	
+ Added console commands RUNESON and RUNESOFF for crctf.cfg.

+ added offhand hook for classic mode (only).
	bind a key to +hook (impulse 97/98).
	will fire hook while holding another weapon.
	fixed a bug in servermoules code that never reset the "backlash" physics
	of the hook, after first fire. Thereafter, made the hook's pull "saggy".
	
+ Added Runes, via request.
	Use SETRUNES to toggle runes.	
	added runes status to rules display.
____________________________________________________________________________

+ Added SetHook command to toggle the hook on or off.
+ Enhanced display of power-ups in the RULES command.
+ Added READY to scoreboard in MATCH mode when player commits to a team. 
+ Added Best Capture Time to Flag Stats. 
+ Buttons/Triggers dont bleed. 
+ Added Damage Taken/Damage Given to KILLSTATS 
+ Smooth Weapon transitions while firing, (id bug) fixed. 
+ Smoother camera if a player walks between objects. 
+ Obituaries reflect watertype when discharging. (water/lava/slime) 
+ Enhanced WARP command supports userdefs.cfg
+ Added delay after VanishHook when hitting teammates with hook.
+ Added PreMatch Capture Time Practice.
+ Armor doesnt deplete while drowning.
+ Fixed E1M3 flag squish bug.
+ Skin errors on Ring of Shadows: (FIXED!)
	Eyes.mdl only has one skin.	
+ Skin errors on Gibs: (FIXED!)
	In old CRCTF 2.8, custom skins for blue team would cause skin errors on 	
	gibs because the skin value was 3 or 4, but the h_player.mdl only 
	has skins 0, 1, and 2.
+ 'Normal' mode is now working!  
	The look and rules are the same as a Classic ThreeWave 3.0 server,
	with all the features CR brings.
    	Non-custom models.
    	Improved check team code.  Players are put on the team with fewer 
    	members or if the team count is the same, they are put on the     	
    	losing team.    
+ When a flagcarrier disconnect/lagsout the flag drops at that origin to the 
  ground. If autopause is activated and the player reconnects and ghostcodes
  back into the game they will regain their old origin ontop of flag where
  they will regain posession when match is unpaused.  
+ Fixed CR's Overtime timer reset bug.
+ All CTF stats are now saved to a clients ghost so they may be restored.  
+ Fixed the CR bug when using bullets or nails to shoot buttons
  your eff will increase.
+ Added powerups to the 'rules' display like in the newer versions of CR. 
+ Fixed automatic request to unpause the match when it is not paused. 
+ ThreeWave skins in match mode. 
+ Fixed all kill stats. 
+ Milliseconds now shown in capture time. 
+ Client's classname and health is now cleared on disconnect
+ Ghost eyes and hovering bodies fixed on client disconnect
+ Removed damage on changelevel_touch for ctf
+ Wrong obituary messages fixed
+ Powerups removed when voted off in "real-time"
+ Better performance in handling of powerups
+ Overall code speed has been greatly increased
+ Correct removal of the chain when passing through teammates
+ Enhanced item_weapon function
+ Improved weapon and powerup touch functions
+ Some weapon name corrections
+ Improved weapon switching on pickups
+ Multiple megahealth rot fixed: follows standard powerup rules for duration and respawn times.
+ Better performance in handling of powerups
+ Thunderbolt fix (never switches on pickup to thunderbolt while underwater)
+ Never switch to weapon pickup while hook is out.
+ Walkframe leak fixed
+ Improved bubble spawn
+ Bubblespawner remove fixed
+ Replaced id's plat_center_touch function with ThreeWave's.  
+ Flag captures are timed
+ Corrected sound channel for flag sounds
+ Double/Inverted telefrag fix
+ Pentagram telefrag fix
+ Fixed id's buggy teleport_touch function that would crash the server
+ hurt_touch fix
+ Backpacks are allowed to be pushed through wind tunnels.
________________________________________________________________________________
todo:
- add ctfxx bsp to levels.qc
________________________________________________________________________________

EOF
