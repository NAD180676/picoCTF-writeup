Author: Will Hong

Level: Medium		| 	category: Cryptography, morse_code

Description:

Morse code is well known. Can you decrypt this?
Download the file [here](https://artifacts.picoctf.net/c/79/morse_chal.wav).
Wrap your answer with picoCTF{}, put underscores in place of pauses, and use all lowercase.

-----------------------------------------------------------------------------------------------------------------------------------------

This challenge can be solved easily with tools online.
If you are an expert at morse code, then this will be a good chance to use your special ability (I've learned multiple times but could never remember;(, if you can, then you're very impressive, keep it up!), if not, then well folks let's seek help from tools.

After we downloaded the file, there will be a 28 seconds long audio, I used [this morse code webite]("https://morsecode.world/international/decoder/audio-decoder-adaptive.html") to decode the audio.

The result is: `WH47 H47H 90D W20U9H7`

so the flag will be in picoCTF{} format, replace space with underscore and words are lowercase:

-----------------------------------------------------------------------------------------------------------------------------------------

picoCTF{wh47_h47h_90d_w20u9h7}
