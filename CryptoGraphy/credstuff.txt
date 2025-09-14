Author: Will Hong / LT 'syreal' Jones
Level: Medium	| 	category: Cryptography


Description:

We found a leak of a blackmarket website's login credentials. Can you find the password of the user CULTIRIS and successfully decrypt it?
Download the leak here (https://artifacts.picoctf.net/c/151/leak.tar).

The first user in usernames.txt corresponds to the first password in passwords.txt. The second user corresponds to the second password, and so on.

-----------------------------------------------***----------------------------------------------

From the description, we got to know the information is that the username and password will have the same line although they are in different files.

So if we could find which line is the CULTIRIS being in, we could trace what is that password look line in the same line number in password file.

First, we can use "wget" command to get the "leak.tar".
Tar is a zip similar file, we can use "tar -xf [filename]" to get what inside of it, the command will be "$tar -xf leak.tar".
We got a folder name "leak", use "cd leak" to change dir, "ls" to see there are 2 files as the author said.

To check which line does "CULTIRIS" being in, we use " $grep -n "cultiris" usernames.txt " (-n will tell which line the cultiris in). Then it will print out "378:cultiris", so let's check what is in line 378 in the password file.

In other to check that, we use "sed -n "[linenumber]p" [filename]", so it will be " $sed -n '378p' passwords.txt ". It will print out "cvpbPGS{P7e1S_54I35_71Z3}"
This looks like a ROT cipher, so let's check on cyberChef with ROT13 and we got the flag: 


picoCTF{C7r1F_54V35_71M3}
