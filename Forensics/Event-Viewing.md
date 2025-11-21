**Author: Venax**

Description:

One of the employees at your company has their computer infected by malware! Turns out every time they try to switch on the computer, it shuts down right after they log in. The story given by the employee is as follows:

  1. They installed software using an installer they downloaded online
  
  2. They ran the installed software but it seemed to do nothing
  
  3. Now every time they bootup and login to their computer, a black command prompt screen quickly opens and closes and their computer shuts down instantly.

See if you can find evidence for the each of these events and retrieve the flag (split into 3 pieces) from the correct logs!
Download the Windows Log file [here](https://challenge-files.picoctf.net/c_verbal_sleep/123d9b79cadb6b44ab6ae912f25bf9cc18498e8addee851e7d349416c7ffc1e1/Windows_Logs.evtx)

-------------------------------------------------------------------------------------------------------------------------------------------

Taking note from the description, we can tell that things started when the employee installed a software online, the software seems to do nothing, but it keeps shutting down when the employee turning on the computer. In that case, getting to know the suspicious software's name will be our first approach.

In order to search thing out easier, I searched `What is the Event ID for installing (software)?`, and it is `11707` for `Successfully INSTALLED the application` and `11724` for `successfully UNINSTALLED the application` 

So we can start our finding with those event with event ID = `11707`

<img width="806" height="223" alt="image" src="https://github.com/user-attachments/assets/06e06c92-7f88-47dc-ba6b-396f4d8b7bb6" />

Checking several events with ID of `11707`, we can see this event which tells us that the computer successfully installed a product name `Totally_Legit_Software` which sounds very legit!

Since it sounds **TOO LEGIT**, we shall follow it, shall we?

Using **FIND** (Ctrl+F) to search things out like document file, using keyword as `Totally_Legit_Software`

<img width="890" height="356" alt="image" src="https://github.com/user-attachments/assets/4e84a3db-fada-4eba-ad8c-35ed8c5c6f7b" />

We got the first part of the flag : `MXNfYV9wcjN0dHlfdXMzZnVsXw==`. With event ID = `4657`, date and time = `7/15/2024 10:56:19 PM`

<img width="901" height="370" alt="image" src="https://github.com/user-attachments/assets/901c4b39-8694-46b2-b471-900771bd1532" />

We got the second part of the flag: `cGljb0NURntFdjNudF92aTN3djNyXw==`. With event ID = `1033`, date and time = `7/15/2024 10:55:57 PM`

Searching till the end of the event logs with keyword `Totally_Legit_Software` but the last part of the flag is nowhere to be found. Take a look at the description, as the author describes that the computer keeps shutting down, so maybe we should look for shut down event that happened.

Using **FIND** (Ctrl+F) to search with keyword `ShutDown`

<img width="870" height="365" alt="image" src="https://github.com/user-attachments/assets/e9d006ca-8ad2-40fd-9ffd-c865f454800f" />

And here we go, the last part of the flag: `dDAwbF84MWJhM2ZlOX0=`. With event ID = `1074`, date and time = `7/16/2024 12:02:35 AM`

Not sure what is the correct to put in the decoder, we can check the `date and time`, first is `cGljb0NURntFdjNudF92aTN3djNyXw==` (since it's on the 15th at 10:55 PM), next is `MXNfYV9wcjN0dHlfdXMzZnVsXw==` (since it's on the 15th and at 10:56 PM), and the last one `dDAwbF84MWJhM2ZlOX0=` (since it's on the 16th).

So our flag will be:

`cGljb0NURntFdjNudF92aTN3djNyXw==MXNfYV9wcjN0dHlfdXMzZnVsXw==dDAwbF84MWJhM2ZlOX0=`

Put in [CyberChef](https://gchq.github.io/CyberChef/) (or any other decoder that you like), using `From Base64` recipe, and we got the flag.

-----------------------------------------------------------------------------------------------------------------------------------------


picoCTF{Ev3nt_vi3wv3r_1s_a_pr3tty_us3ful_t00l_81ba3fe9}
