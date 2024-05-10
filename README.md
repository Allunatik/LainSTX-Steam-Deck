# LainSTX-Steam-Deck

## About
This is a guide on how to setup LainTSX on the Steam Deck locally
[https://laingame.net/](https://laingame.net/)

The process is simple. A custom shell script is ran that launches the webserver provided with LainTSX

# Initial setup
This guide assumes you have a flatpak Chrome web browser installed on your Steam Deck trough the Discover store, if you don't you should first do so. If you wish to substitute the browser to another you will need to substitute the browser specific command at the end of the script with your own.

## Setup manually
- Download the [Offline install](https://laingame.net/offline.html) version of Laingame.com
- Grab the script from [Releases](https://github.com/Allunatik/Tsukihime-Trial-Edition-1999-EN-TL/releases)
- Create a folder in your Steam folder, we'll use LainTSX for the sake of this guide in 
  The path should be /home/deck/.local/share/Steam/steamapps/common/LainTSX
- Paste ```laingame.com``` into the folder
- Paste ```lainlocal.sh``` into the folder
- Make lainlocal.com executable by right clicking ```lainlocal.com``` > properties > permissions > is executable > ok
- Make the script executable by right clicking ```lainlocal.sh``` > properties > permissions > is executable > ok

Alternatively you can open konsole by right clicking the folder ```Open Terminal Here``` chmod+x and drag-dropping the file(s) into the terminal

-Add the script ```lainlocal.sh``` as a non-steam game

Thats it you're done, see the sections "Post install" and "Additional".

## Setup manually
This part assumes you're partially familiar with how to navigate and do simple tasks in Linux, it's a good way to learn how this script works and how to setup a non-steam game in general.

- Download the [Offline install](https://laingame.net/offline.html) version of Laingame.com
- Create a folder in your Steam folder, we'll use LainTSX for the sake of this guide in 
- The path should be /home/deck/.local/share/Steam/steamapps/common/LainTSX
- Paste laingame.com into the folder
- Create a new text file called ```"lainlocal.sh"```
- Open "lainlocal.sh" with a text editor in this case we'll use KDE's default "Kate"

- Add #!/bin/bash to the first line of the script
- Add the path to the webserver, assign a port with "-p" at the end ```/home/deck/.local/share/Steam/steamapps/common/LainSTX/laingame.com -p 8081```
- We'll use 8081 as an example as 8384 is reserver for the Decky loader plugin however you may use whatever port you wish
(Alternatively if you don't wish to host it manually for whatever reason you can just point it to the official host ```https://3d.laingame.net/#/game``` by replacing the above line)

- Then lastly point the web browser to open your locally hosted LainTSX in kiosk mode by adding
```& flatpak run --command=/app/extra/chrome com.google.Chrome --no-sandbox --kiosk http://127.0.0.1:8081/#/game```


The final script should look something like
```
#!/bin/bash
/home/deck/.local/share/Steam/steamapps/common/LainSTX/laingame.com -p 8081 & flatpak run --command=/app/extra/chrome com.google.Chrome --no-sandbox --kiosk http://127.0.0.1:8081/#/game
```
- Make lainlocal.com executable by right clicking ```lainlocal.com``` > properties > permissions > is executable > ok
- Make the script executable by right clicking ```lainlocal.sh``` > properties > permissions > is executable > ok

Alternatively you can open konsole by right clicking the folder ```Open Terminal Here``` chmod+x and drag-dropping the file(s) into the terminal

- Add the script ```lainlocal.sh``` as a non-steam game

Thats it you're done, see the sections "Post install" and "Additional".

## Post install
- Download the control scheme "LainTSX" in the community layouts section for mapped controls
- The left trackpad has touch menu hotkeys for zooming the game to "Fullscreen" and it's regular window size

## Additional
- Install Decky loader and the plugin SteamGridDB to add artwork easily trough Gamemode if you don't already have them
[Decky Loader](https://github.com/SteamDeckHomebrew/decky-loader)
