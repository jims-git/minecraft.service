# minecraft.service
This will launch minecraft as a service at startup.

 Folder Structure
 ================
 minecraft/
 ├── banned-ips.json
 ├── banned-players.json
 ├── bu
 │   ├── daily
 │   └── hourly
 ├── error.log
 ├── eula.txt
 ├── libraries
 ├── logs
 ├── ops.json
 ├── scripts
 │   ├── mcbu.sh
 │   ├── minecraft.service   <---- this files location
 │   └── run.sh
 ├── server.jar
 ├── server.properties
 ├── usercache.json
 ├── versions
 ├── whitelist.json
 └── world

cd ~/minecraft/scripts
Save this file to ~/minecraft/scripts/ and then : 
sudo systemctl daemon-reload
sudo systemctl enable minecraft


systemctrl commands
---------------------------
sudo systemctl daemon-reload                # This command tells Linux there is a new/modified Service available.
sudo systemctl start minecraft
sudo systemctl status minecraft
sudo systemctl enable minecraft             # This command tells Linux to launch at startup.
sudo systemctl disable minecraft.service    # This command tells Linux to NOT launch at startup.
service minecraft status
journalctl -fu minecraft.service

sudo service minecraft stop                 # gracefully shutdown the server


You can connect to the screen minecraft is running in to give in-game commands:
jim@ms:~/minecraft$ screen -ls
There is a screen on:
        103821.Server1  (01/31/2024 11:11:25 PM)        (Detached)
1 Socket in /run/screen/S-jim.

jim@ms:~/minecraft$ screen -R Server1

Use <ctrl>-a d to exit the screen.
Use <ctrl>-a k to kill the screen.


cd /etc/systemd/system/
ls
You should see minecraft.service in the list.
If you modify the file here, you will need to: sudo systemctl daemon-reload
