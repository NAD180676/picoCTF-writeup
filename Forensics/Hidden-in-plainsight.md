**Author: Yahaya Meddy**

Description:

You’re given a seemingly ordinary JPG image. Something is tucked away out of sight inside the file. Your task is to discover the hidden payload and extract the flag.
Download the jpg image [here](https://challenge-files.picoctf.net/c_amiable_citadel/f4d19218cb65d748b6a9b2bfc75caf5ac578f71e284ade9ee300e7367a5df648/img.jpg).

-----------------------------------------------------------------------------------------------------------------------------------------

Open it up, everthing seems normal, the hint tell us to check the metadata, let's check it out, we can use [Hexedit](https://hexed.it/) or xxd command
`xxd img.jpg | head`

As we can see, there is some odd data from 0x1 to 0x3

    00000000: ffd8 ffe0 0010 4a46 4946 0001 0100 0001  ......JFIF......
    00000010: 0001 0000 fffe 001e 6333 526c 5a32 6870  ........c3RlZ2hp
    00000020: 5a47 5536 5930 5647 4e6d 5675 5a48 5a6a  ZGU6Y0VGNmVuZHZj
    00000030: 6256 4539 ffdb 0043 0008 0606 0706 0508  bVE9...C........
    00000040: 0707 0709 0908 0a0c 140d 0c0b 0b0c 1912  ................
    00000050: 130f 141d 1a1f 1e1d 1a1c 1c20 242e 2720  ........... $.' 
    00000060: 222c 231c 1c28 3729 2c30 3134 3434 1f27  ",#..(7),01444.'
    00000070: 393d 3832 3c2e 3334 32ff db00 4301 0909  9=82<.342...C...
    00000080: 090c 0b0c 180d 0d18 3221 1c21 3232 3232  ........2!.!2222
    00000090: 3232 3232 3232 3232 3232 3232 3232 3232  2222222222222222

Decode it from Base64: `echo 'c3RlZ2hpZGU6Y0VGNmVuZHZjbVE9' | base64 -d`, we get `steghide:cEF6endvcmQ=`, which may hint us into using steghide to extract data from the image

Decode once again to get the password, `echo 'cEF6endvcmQ=' | base64 -d`, we get `pAzzword` as the password and now use stehide to extract data `steghide extract -sf img,jpg -p pAzzword`, it will extract a `flag.txt` file.
`cat flag.txt` and we got the flag.

-----------------------------------------------------------------------------------------------------------------------------------------


picoCTF{h1dd3n_1n_1m4g3_5d4cba73}
