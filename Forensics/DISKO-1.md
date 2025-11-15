**Author: Darkraicg492**

Description:
Can you find the flag in this disk image?
Download the disk image [here](https://artifacts.picoctf.net/c/538/disko-1.dd.gz).

------------------------------------------------------------------------------------------------------------------------------------------------------------------

`Maybe Strings could help? If only there was a way to do that?`, use `Strings`  with `grep` for easier find

After downloading the file, use `gunzip [filename]` to unzip it, then `strings [filename] | grep picoCTF`, then we get the flag

------------------------------------------------------------------------------------------------------------------------------------------------------------------

picoCTF{1t5_ju5t_4_5tr1n9_e3408eef}
