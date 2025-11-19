**Author: Shuailin Pan (LeConjuror)**


Description:

RED, RED, RED, RED
Download the image: [red.png](https://challenge-files.picoctf.net/c_verbal_sleep/831307718b34193b288dde31e557484876fb84978b5818e2627e453a54aa9ba6/red.png)

------------------------------------------------------------------------------------------------------------------------------------------------------------------

After downloaded the photo, even though we can get some data from using `exift tool`, however, it's just a poem with nothing related to the flag. So in this case, we will use another tool, maybe zsteg or steghide, but using [AperiSolve](www.aperisolve.com/) may be the best choice in this case.

Just simply put the photo in the box, then hit `submit`, it will do all kind of extract data to the image.

Scroll down to the `Zsteg` section, we can see at the location `b1,rgba,lsb,xy `, it contains text type data: `cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==`

Put it in [CyberChef](https://gchq.github.io/CyberChef/), use `From Base64` recipe, and finally, here is the flag.

------------------------------------------------------------------------------------------------------------------------------------------------------------------

picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}
