Forensics

Author: Prince Niyonshuti N.

Description:

Hi, intrepid investigator! 📄🔍 You've stumbled upon a peculiar PDF filled with what seems like nothing more than garbled nonsense. But beware! Not everything is as it appears. Amidst the chaos lies a hidden treasure—an elusive flag waiting to be uncovered.
Find the PDF file here [Hidden Confidential Document](https://challenge-files.picoctf.net/c_amiable_citadel/5618b8a659b50b6ac50c1cb90bb61d75775299df46921871cd8cdc7888c9d509/confidential.pdf) and uncover the flag within the metadata.

--------------------------------------------------------------------------------------------------------------------------------------------

As the description mentioned, in order to get the flag, we should investigate the metedata. Taking this hint, I will put it in [Hexedit](https://hexed.it/) to see the metadata.

I can see the odd data start from the address 0x7 to 0xA, which is
  "cGljb0NURntwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV9jOGY5MWQ2OH0"

I try decoding it from Base64 at [CyberChef](https://gchq.github.io/CyberChef/), with the "From Base64" recipe, 

And there we go, the flag is there.

-----------------------------------------------------------------------------------------------------------------------------------------


flag: picoCTF{puzzl3d_m3tadata_f0und!_c8f91d68}
