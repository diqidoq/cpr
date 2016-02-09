# cpcam

A bash script terminal utility to auto-sync between injected cam cards (e.g. photo, film) and local backup structures.

## Install instructions

All @diqidoq bash script utilities are build the same way: Create a ``` ~/share ``` and a ``` ~/bin ``` folder in you machines user account if it doesn't exist already (``` mkdir -p ~/<folder> ```) and ``` git clone ``` the repo into the ``` ~/share ``` folder. Then create a sym link from the main executable file commonly named like the repo in ``` ~/share/<the-new-utility-git> ``` to the ``` ~/bin/<executable> ``` folder and ``` chmod a+x ~/bin/<executable> ```. Make sure your ``` ~/bin ``` folder is in the system path (``` export PATH=/home/yourusername/bin:PATH ```) to make the new utility terminal aware for commands.

    mkdir -p ~/bin
    mkdir -p ~/share
    cd ~/share
    git clone <this-git-repo> (link from above on the right <https>)
    ln -s ~/share/<this-git-repo>/<this-utility-name> ~/bin/<this-utility-name>
    chmod a+x ~/share/<this-git-repo>/<this-utility-name> ~/bin/<this-utility-name>
    source ~/.bashrc

## Requirements

 + git (``` sudo apt-get install git ```)
 + Bash (Born Again Shell support)
 + X enviroment with Xterm like terminals, like default in Debian/Ubuntu derivates and Mac OSX systems.
 + FFmpeg, mplayer or mediainfo installed for media info support
 + USB ports for external cards and USB storage to import
 + Some basic knowledge about terminal commands and terminal application handling.

## What it does

 + It checks if the in config-file provided source- and base target-devices and dirs exist and if source dir is not empty.
 + Creates date and time stamp sub dir in target base dir to make a unique target dir available.
 + It uses rsync to create a local copy of the file structure on target from source and compares afterwards with verbose output.
 + Target dirs get time stamp and log files about time and media on import.
 + Opens your file manager to show you source and target and prints some info about both to make sure the import was complete.
 + Breaks up if one the 2 directories are suspicious in any way and warns you about it
 + Finally asks you if you want the source to get cleaned

## How it works

 + Simply drag your cam card into the cardreader slot or card reader USB dongle and connect it to the system
 + modify the cpcam.cfg to enter/modify SOURCE and TARGET dir, if not already done after first cpcam run dialoque
 + Now simply open terminal and type ``` cpcam ```
 + That's it. cpcam will sync both directories and will show you that import was successful.
