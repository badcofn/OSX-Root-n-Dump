# OSX-Root-n-Dump
USB Rubber Ducky payload to insert osx backdoor and dump keychain data.

To use:
Boot into single user mode 'Command + S' and insert ducky at root# . 
This script will created a persistent backdoor as the root user then setup a script to download the keychaindump file when an internet connection is made after boot. It then saves the keychain dump file to /Library/.hidden/$user.login.keychain.txt 
Change to your IP address or domain name and port number and catch with nc -l -p [port no.]
You may want to compile and host your own version of keychaindump, i am using the version from the original script found below.

About the scripts modified to create this payload:

Keychaindump-

Is a proof-of-concept tool for reading OS X keychain passwords as root written by Juuso Salonen. It hunts for unlocked keychain master keys located in the memory space of the securityd process, and uses them to decrypt keychain files.
You can find it here: https://github.com/juuso/keychaindump

DuckDump-

Utilises Keychaindump and dumps all user passwords upon user login.
You can find the standalone duckscript here: https://github.com/IsaiahJTurner/duckdump

OSX Root Backdoor-

Author - Patrick Mosca

Boot into single user mode and insert ducky. This script will created a persistent backdoor as the root user. 
Change to your IP address or domain name and port number.
You can find the standalone duckscript here: https://github.com/hak5darren/USB-Rubber-Ducky/wiki/Payload---OSX-Root-Backdoor

Cleanup:

The following 5 files will be created:

/Library/LaunchDaemons/com.apples.services.plist

/Library/LaunchDaemons/com.apples1.services.plist

/Library/.hidden/*.sh 

/Library/.hidden/keychaindump
/Library/.hidden/$user.login.keychain.txt

