Author: Will Hong

Level: Medium		| 	category: Cryptography, cryptography

Description:

Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message.
Download the corrupted message [here](https://artifacts.picoctf.net/c/193/message.txt).

-----------------------------------------------------------------------------------------------------------------------------------------

Content in messages.txt:

	heT fl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V9AAB1F8}7

-----------------------------------------------------------------------------------------------------------------------------------------

To decode it, look at those first blocks of char, I see a pattern, which is the third char will have to move to the first, then the other two will be push back:

	example: heT		The letter T will be push in front of 'he', and 'he' will be pushed backward => 'The'

Applying those pattern to solve from the beginning of the line confusing me, so I decided to solve it backward, I counted 3 letters, it will be one block, then just simply put the last char of each block to the front of it, then move to the next block

				example: 8}7 	=>	78}
					 B1F	=>	FB1
					...	=>	...
	
You can either try to decode by hand or just use Python program for decryption:

		corrupted = "heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V6E5926A}4"
		flag = ""
		 
		blocks = (corrupted[i:i+3] for i in range(0, len(corrupted), 3))
		
		for block in blocks:
		    flag += block[2]+block[0]+block[1]
		
		print(flag)

-----------------------------------------------------------------------------------------------------------------------------------------


picoCTF{7R4N5P051N6_15_3XP3N51V3_A9AFB178}
