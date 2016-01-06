## Dont Starve together dedicated server, automated creation

+ credit process to http://dont-starve-game.wikia.com/wiki/Guides/Don%E2%80%99t_Starve_Together_Dedicated_Servers#On_Linux_.28Debian.29  :)

### the steps needed as compiled from the above credits to go into the script:
###### (assuming debian64 because it's the best, fuck you lol)
apt-get install lib32gcc1
###### user changed to dontsuck because it's funnier
adduser dontsuck
###### deps needs, updates, i386 arch, and woo things
dpkg --add-architecture i386
apt-get update ; apt-get upgrade -y
apt-get install -y lib32gcc1 lib32stdc++6 libcurl4-gnutls-dev:i386
###### steamcmd (using a proper source. as provided from https://developer.valvesoftware.com/wiki/SteamCMD
chmod a+rw `tty`
sudo -u dontsuck -c 'mkdir ~/steamcmd ;\
    cd ~/steamcmd ;\
    wget http://media.steampowered.com/installer/steamcmd_linux.tar.gz ;\
    tar -xvzf steamcmd_linux.tar.gz ;\
    mkdir -p /home/dontsuck/app ;\
    ./steamcmd.sh ;\
        login anonymous ;\
        force_install_dir /home/dontsuck/app ;\
        app_update 343050 validate ;\
        quit'
#### exeeeeeecutable will live at: ~dontsuck/app/DST/bin/dontstarve_dedicated_server_nullrenderer

