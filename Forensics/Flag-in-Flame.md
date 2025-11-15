**Author: Prince Niyonshuti N.**

Description:

The SOC team discovered a suspiciously large log file after a recent breach. When they opened it, they found an enormous block of encoded text instead of typical logs. Could there be something hidden within? Your mission is to inspect the resulting file and reveal the real purpose of it. The team is relying on your skills to uncover any concealed information within this unusual log.
Download the encoded data here: [Logs Data](https://challenge-files.picoctf.net/c_amiable_citadel/34c1721086e2555cb8df9a09fcad35cfc09a2844bbc990dd022efca838b4e6ea/logs.txt). Be prepared—the file is large, and examining it thoroughly is crucial.

--------------------------------------------------------------------------------------------------------------------------------------------

After downloading the file, we have a `logs.txt` file, it contains lots of unreadable data and as the hint given `Use base64 to decode the data and generate the image file.` This will be easy enough if we use tool, the best one to go for is [CyberChef](https://gchq.github.io/CyberChef/)

Here in CyberChef, we just put the `logs.txt` file here, then use `from Base64` recipe, it will decode the data and as I noticed the header showing `PNG`, so I just know that this is just the raw data of an imgae, in order to see the image, use `Render Image` recipe.

We will see a line of number : `7069636F4354467B666F72656E736963735F616E616C797369735F69735F616D617A696E675F61633165333538347D`

Put in [CyberChef](https://gchq.github.io/CyberChef/) again and use `From Hex` recipe, and we got the flag.

-----------------------------------------------------------------------------------------------------------------------------------------

picoCTF{forensics_analysis_is_amazing_ac1e3584}
