Author: Sanjay C/Daniel Tunitis

Level: Medium		| 	category: Cryptography

Description:

Decrypt this message (https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext).

-----------------------------------------***------------------------------------------------------------

Once we open the file, we have the text:

	picoCTF{ynkooejcpdanqxeykjrbdofgkq}

As the challenge name, it gonna be a ROT cipher decoding, just simply use decoder online to help us:
	https://www.dcode.fr/rot-cipher
or
	https://gchq.github.io/CyberChef/


As the first link, we simply paste in and it will do all the work, however in CyberChef, when put the ROT13 recipe in, the decoded text seems incorrect, so I increased the amount and got the correct decoded text at the amount of 30
So the flag will be:


picoCTF{crossingtherubiconvfhsjkou}






