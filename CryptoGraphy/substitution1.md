Author: Will Hong

Level: Medium	| 	category: Cryptography, Substitution_cipher

Description:

A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again.
Download the message [here](https://artifacts.picoctf.net/c/181/message.txt).

-----------------------------------------------------------------------------------------------------------------------------------------


File content:


    ZWDg (gejfw djf zacwpfx wex dqar) afx a wscx jd zjicpwxf gxzpfbws zjicxwbwbjv. Zjvwxgwavwg afx cfxgxvwxm hbwe a gxw jd zeaqqxvrxg     hebze wxgw wexbf zfxawbybws, wxzevbzaq (avm rjjrqbvr) gnbqqg, avm cfjtqxi-gjqybvr atbqbws. Zeaqqxvrxg pgpaqqs zjyxf a vpitxf jd zawxrjfbxg, avm hexv gjqyxm, xaze sbxqmg a gwfbvr (zaqqxm a dqar) hebze bg gptibwwxm wj av jvqbvx gzjfbvr gxfybzx. ZWDg afx a rfxaw has wj qxafv a hbmx affas jd zjicpwxf gxzpfbws gnbqqg bv a gadx, qxraq xvybfjvixvw, avm afx ejgwxm avm cqasxm ts iavs gxzpfbws rfjpcg afjpvm wex hjfqm djf dpv avm cfazwbzx. Djf webg cfjtqxi, wex dqar bg: cbzjZWD{DF3LP3VZS_4774ZN5_4F3_Z001_4871X6DT}
  

Similar to substitution0, maybe an online tool can help. Let use [this](https://planetcalc.com/8047/)

After decoding, we got the flag: 

`picoCTF{FR3JU3NCY_4774CK5_4R3_C001_4871E6FB}`

However, when I entered the flag, it said the flag is incorrect, so I try to understand if the words in the flag are correct, I noticed the word `FR3JU3NCY` which similarly mean `FREQUENCY` but the `Q` got replaced by the `J`, so I change it to `FR3QU3NCY` and it is correct.

-----------------------------------------------------------------------------------------------------------------------------------------

picoCTF{FR3QU3NCY_4774CK5_4R3_C001_4871E6FB}
