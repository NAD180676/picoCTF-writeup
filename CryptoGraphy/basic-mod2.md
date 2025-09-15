Author: Will Hong

Level: Medium		| 	category: Cryptography

Description:

A new modular challenge!
Download the message here (https://artifacts.picoctf.net/c/179/message.txt).
Take each number mod 41 and find the modular inverse for the result. Then map to the following character set: 1-26 are the alphabet, 27-36 are the decimal digits, and 37 is an underscore.
Wrap your decrypted message in the picoCTF flag format (i.e. picoCTF{decrypted_message})

-----------------------------------------***------------------------------------------------------------

This challenge is similar to the previous one, basic-mod1 . The different here is the index of alphabet, decimal and underscore, all of it has been increase by 1. And the second different is instead of finding the normal modular, this one is about MODULAR INVERSE. You can check out what is Modular inverse online.

This can also be solved by hand but it will take a lot of time since we have to calculate every single inverse of every modular, so we use python instead.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------
def basicMod2():

    char=" ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789_"
    messages=[104,372,110,436,262,173,354,393,351,297,241,86,262,359,256,441,124,154,165,165,219,288,42]

    for i in range(len(messages)):
        print(char[inverse(messages[i],41)], end="")

def inverse(nums, modular):
    for x in range(1, modular):
        if(((nums % modular) * (x % modular))% modular == 1):
            return x
    return -1
    
    
basicMod2()
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------


Similar to the previous one, however here I create one more function called inverse which will inverse the modular, then char will point to that index

And finally, we got the flag:


picoCTT{1NV3R53LY_H4RD_DADAACAA}



