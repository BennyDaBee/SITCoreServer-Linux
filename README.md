# SITCoreServer-Linux
## How to Install SITCore Server Mod for Linux for Current Version 3.6.1
###### I used ubuntu so this will work for Ubuntu. (Tested using Ubuntu 22.04 with Desktop)

## Prerequisites (Which will be covered)
1. Lutris
2. Wine
3. A Legal Copy of EFT
4. SITCore Server Files

## Installing Lutris and Wine
#### This will differ for other Linux Distros, so please lookup your steps for your distro. 

### Installing Wine
#### Run the following Commands

  1. sudo dpkg --add-architecture i386
  2. wget -nc https://dl.winehq.org/wine-builds/winehq.key
  3. sudo apt-key add winehq.key
  4. sudo apt-add-repository 'deb https://dl.winehq.org/wine-builds/ubuntu/ focal main'
  5. sudo apt update
  6. sudo apt install --install-recommends winehq-stable

### Installing Lutris
#### Run the Following Commands

1. sudo add-apt-repository ppa:lutris-team/lutris
2. sudo apt update
3. sudo apt install lutris

You should now see Lutris in the install applications. 

### Prepping the Server Files
#### THIS WOULD BEST BE DONE ON A WINDOWS PC BEFORE MOVING IT TO THE LINUX PC
1. Download SPT-AKI from [here](https://www.sp-tarkov.com/)
2. Extract AKI.Server and Aki_Data to a dedicated folder
3. Run the AKI.Server.exe so that it makes the `user` folder
4. Download the Latest version of SITServer Mod from [here](https://github.com/paulov-t/SIT.Aki-Server-Mod/releases)
5. Exctract the mod, rename it to SITCoop, and place it in the `user\mods` folder.
6. Download the SITPatcher from [here](https://github.com/T4s3rF4c3/SIT-Patcher-Troubleshoot/raw/20b83780f1c5f0b94685c0c38b299c640db856bb/BIN/x64/SIT-Patcher-Troubleshoot.exe)
7. Extract and Run the SITPatcher
8. Since this is only a guide for server install, click on Set SIT-Server Folder and specify the folder in which you have the Aki.Server and Aki_Data
9. Click on Patch-ALL for SPT-AKI 3.6.1
10. Click yes on the next box that appears

### Installing the Server
1. Now we should be able to move it to the linux machine, I personally would use 7zip, compress the file, upload it to google drive, and then download it from drive onto the machine.
2. Open Lutris, then at the top left, click the plus icon, then click Search Lutris
3. Search for Escape from Tarkov
4. Click on it
5. Click on Install for Officical
6. After it is installed, browse to `/home/*USERNAME*/Games/escape-from-tarkov/drive_c/`
7. Create a new folder, I called mine SIT-Server
8. Extract the sever files into that folder
9. In Lutris, right click on the Escape From Tarkov, and click duplicate
10. On the duplicate, right click and then click Configure
11. I would change the name to something like SIT-Server
12. Change the Directory to the Folder that you extracted the server files into
13. Go to Game Options, and change the Executable to the AKI.Server.exe file
14. In Runner Options, Set the Wine Version to wine-ge-8-16-x86_64
15. In System Options, turn on Advanced then scroll down till you see Use CLI Mode, and turn it on, then click save
16. Click on the up arrow next to the wine glass at the bottom of Lutris when you have the server selected, then click Wine Configuration
17. Change Windows Version to Windows 10
18. Click the Libraries Tab, and in the "New override for library" add `winhttp`, click add, and then apply


### Modifying for External Connections
1. Run the Server from Lutris and you should see a window open, when it says something like "Happy Playing" Close it
2. There will be 2 files we have to modify in the Server Files
3. In `user/mods/SITCoop/configs` there will be a coopConfig.json file
4. You will need to modify the IP address to your external IP
5. In `Aki_Data/Server/configs` there will be a http.json file
6. Change the IP Address to your external IP address
####If Running Locally, you will need to port forward 6969 and 6970 to your server, if using a VPS you should not have to

# You Should now be able to launch the Server and people should now be able to connect
## There is a discord server for support, but they may not be able to assist with the linux portion. You can find the discord [here](https://discord.gg/VengzHxNmZ)
