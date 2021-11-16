## Clanring Threewave Capture the Flag mod for Netquake (Proquake based servers)

This deployment of CRCTF swaps out cmaps.exe and cmaps.cfg for the more well documented Crmake which provides macOS and Linux binaries.
The rationale is that the source code for Crmake is widely available (via CRMOD/utils) and thus there are both Linux, Windows and macOS binaries.

To start your CRCTF server it's recommended you use manquake (which is headless Linux Proquake + Slotzero's patches):

- Put these files into a gamedir called "crctf" with manquake being one step down such as:
./quake/
./quake/manquake
./quake/crctf/

- Execute the server with the gamedir:
- ./manquake -mem 256 -dedicated 16 -game crctf -zone 1024 -port 26001 -condebug logs/"$(date +\%Y-\%m-\%d-\%H)"
- Every time you make any change to the custom maps you will need to execute Crmake (windows, mac, or linux). This will recompile progs.dat (the mod binary code).


FAQ:
- Why use manquake and not sqpro?
this version of crctf has certain incompatibilities with anticheat code which render it slower / less efficient on sqpro so manquake is recommended
- Should I use manquake for TDM servers too?
maybe. I haven't fully investigated the reasons those two forks differ in performance and can't really tell which is better. at least manquake is actively maintained by slotzero, vs. sqpro is no longer maintained by Baker because he is MIA.
