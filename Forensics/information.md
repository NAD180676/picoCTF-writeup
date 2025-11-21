**Author: susie**

Description:
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/7cf6a33f90deeeac5c73407a1bdc99b6/cat.jpg)

--------------------------------------------------------------------------------------------------------------------------------------------

To work with photo, the first thing we should do is to check the metadata of it. We can use `exif tool` to extract data, or use [AperiSolve](www.aperisolve.com/) or even [HexEdit](https://hexed.it/) (although it is a little hard to check the metadata with hexedit, it still work fine).

Just put the photo in the tools, we can see an odd data at `License`.

It is `cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9`

Put in [CyberChef](https://gchq.github.io/CyberChef), use `From Base64` recipe, then we got the flag.

--------------------------------------------------------------------------------------------------------------------------------------------

picoCTF{the_m3tadata_1s_modified}
