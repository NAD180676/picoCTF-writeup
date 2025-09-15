Author: Will Hong

Level: Medium		| 	category: Cryptography, cryptography

Description:

Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message.
Download the corrupted message here (https://artifacts.picoctf.net/c/193/message.txt).

-----------------------------------------***------------------------------------------------------------
Content in messages.txt:
	heT fl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V9AAB1F8}7

------------------------------------------------------------------------------------------------------------------------------------------------------

As the description mentioned, in this txt file, block of 3 chars are got scrambled around, so in other to solve this, we have to rearrange those letters in every blocks, you can either find a python program to decode it, somehow no matter how hard i try to run, it keeps showing error, even i tried other authors' python decode, somehow it still doesn't work for me.

Fortunately, I figure out a way to decode by hand pretty easy, look at those first blocks of char, I see a pattern, which is the third char will have to move to the first, then the other two will be push back:

				example: heT		The letter T will be push in front of 'he', and 'he' will be pushed backward => 'The'

Applying those pattern to solve from the beginning of the line confusing me, so I decided to solve it backward, I counted 3 letters, it will be one block, then just simply put the last char of each block to the front of it, then move to the next block

				example: 8}7 	=>	78}
					 B1F	=>	FB1
					...	=>	...


Continuously doing it until I reach the the word picoCTF, then I got the flag:



picoCTF{7R4N5P051N6_15_3XP3N51V3_A9AFB178}




