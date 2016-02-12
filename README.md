ES-scraper
=====================
```
usage: scraper.py [-h] [-w value] [-noimg] [-v] [-f] [-crc] [-p]

ES-scraper, a scraper for EmulationStation

optional arguments:
  -h, --help  show this help message and exit
  -w value    defines a maximum width (in pixels) for boxarts (anything above
              that will be resized to that value)
  -noimg      disables boxart downloading
  -v          verbose output
  -f          force re-scraping (ignores and overwrites the current gamelist)
  -crc        CRC scraping
  -p          partial scraping (per console)
  -m          manual mode (choose from multiple results)
  -newpath    gamelist.xml & boxart are written in $HOME/.emulationstation/%NAME%/
  -fix        temporary thegamesdb missing platform fix
  -c file     Specify es_system.cfg file (defaults to
              $HOME/.emulationstation/es_systems.cfg)
```

Quick script written in Python that uses various online sources to scrape artwork and game info and saves it as XML files to be read by EmulationStation.

If you haven't done so, please update ES before running this script.

For image resizing to work, you need to install PIL:
```
sudo apt-get install python-imaging
```

Usage
=====================
* Open your systems config file ($HOME/.emulationstation/es_systems.cfg) and append the corresponding [platform ID](#platform-list) to each system:

```
<system>
  <name>nes</name>
  <fullname>Nintendo Entertainment System</fullname>
  <path>~/ROMS/NES/</path>
  <extension>.nes</extension>
  <command>retroarch -L /path/to/core %ROM%</command>
  <platform>nes</platform>
  <theme>nes</theme>
  <platformid>7</platformid>
</system>
```

* Run the script.

Platform List
=====================
Below is a list of all available platforms in the database and their IDs.

```
[25] 3DO
[4911] Amiga
[23] Arcade
[22] Atari 2600
[26] Atari 5200
[27] Atari 7800
[28] Atari Jaguar
[29] Atari Jaguar CD
[30] Atari XE
[31] Colecovision
[40] Commodore 64
[32] Intellivision
[37] Mac OS
[14] Microsoft Xbox
[15] Microsoft Xbox 360
[24] NeoGeo
[4912] Nintendo 3DS
[3] Nintendo 64
[8] Nintendo DS
[7] Nintendo Entertainment System (NES)
[4] Nintendo Game Boy
[5] Nintendo Game Boy Advance
[41] Nintendo Game Boy Color
[2] Nintendo GameCube
[9] Nintendo Wii
[38] Nintendo Wii U
[1] PC
[33] Sega 32X
[21] Sega CD
[16] Sega Dreamcast
[20] Sega Game Gear
[18] Sega Genesis
[35] Sega Master System
[36] Sega Mega Drive
[17] Sega Saturn
[10] Sony Playstation
[11] Sony Playstation 2
[12] Sony Playstation 3
[39] Sony Playstation Vita
[13] Sony PSP
[6] Super Nintendo (SNES)
[34] TurboGrafx 16
```
