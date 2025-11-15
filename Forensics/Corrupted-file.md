**Author: Yahaya Meddy**

Description:
This file seems broken... or is it? Maybe a couple of bytes could make all the difference. Can you figure out how to bring it back to life?
Download the file [here](https://challenge-files.picoctf.net/c_amiable_citadel/913cc89502ac17f0c3cb28c10eff77ca19d19b5e5bce22ff24775a6825b6f2d3/file)

------------------------------------------------------------------------------------------------------------------------------------------------------------------

After downloading the file, it is just a normal data file with no recognizable file type, then I put it in [Hexedit](https://hexed.it/), to check the raw data of it, as it appears at the first line the `JFIF` which is the header format for JPEG img.

And JPEG header in hex normally appear as: `FF D8 FF E0 00 10 4A 46 49 4600 01 01 00 01 00 01 00 00`, however the file we just download, its header start with `5C 78` which is incorrect, that may be the reason the file is corrupted, so change it to `FF D8` and save it then reopen again, we will see the flag.

------------------------------------------------------------------------------------------------------------------------------------------------------------------

picoCTF{r3st0r1ng_th3_by73s_752d2c00}

