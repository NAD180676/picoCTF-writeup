Author: Will Hong

Level: Medium		| 	category: Cryptography

Description:

We found this weird message being passed around on the servers, we think we have a working decryption scheme.
Download the message here (https://artifacts.picoctf.net/c/127/message.txt).
Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.
Wrap your decrypted message in the picoCTF flag format (i.e. picoCTF{decrypted_message})

-----------------------------------------***------------------------------------------------------------

This challenge can be solved by hand following the instruction from the description, or we can just simply code a simple decrypt file. Python will come in handy.

Mod is dividing but taking the remainder instead of the result
As we have from the description, the alphabet will be from 0 to 25, 26 to 35 will be numbers and 36 will be an underscore

Taking all that information, we can write a python look likes this:

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------
def basicMod():
    char = "ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789_" 

    messages = [128,322,353,235,336,73,198,332,202,285,57,87,262,221,218,405,335,101,256,227,112,140]		//this is from the message file

    for i in range(len(messages)):						//loop through the whole messages list
            print(char[messages[i]%37], end="")			//each char of messages will be moded by 37, then that result will be put 																//inside char, so that
														//it will point to the direct position
														//example: 128%37= 17, so char[17]=R and so on. end="", that will remove space 															//between chars.
basicMod()
----------------------------------------------------------------------------------------------------------------------------------------------------------------------

After decoding, we have: R0UND_N_R0UND_79C18FB3. So the flag will be


picoCTF{R0UND_N_R0UND_79C18FB3}




