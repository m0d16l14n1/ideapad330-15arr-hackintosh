# Guide for unlocking InsydeH20 bios on your LENOVO IDEAPAD 330-15ARR (might work on other Lenovo with Insyde, but i am not sure and not responsible for any kind of bricks and other stuff)

# What you will need: 

1) UEFITool (not Alpha versions, only stable ex - https://github.com/LongSoft/UEFITool/releases/tag/0.28.0) 
Note, that we will need only UEFITool, not other of UEFIPatch, Extract and whatsoever. 

2) CH34A1 programmer with clip. (Note, you will need clip, if you don't want to solder bios chip into programmer)

3) Hex editor with comparison function (that's is really needed, will make process easier, ex - HxD is okay)

# Let's start

1) Teardown your laptop, disconnect battery cable (I am usually removing it from laptop to be sure, it's really unplugged, lol)

2) Install CH34A1 software and drivers. Please, don't miss that point, it will fix 99% further questions about fails in flashing bios

3) Connect the clip to the bios chip. It's located near battery, has 8 "legs" and a little white line (remember that white line)
On your clip you will see wires. One will be red or different color from the others. Mine is red. So, you should check before connection to match that red wire with white line near bios chip

4) Connect CH34A1 to PC, open software. 

5) Click "Read". Wait until process is finished. 

6) Click "Save", name bios like you want to name it (ex. dumped.bin) 
PLEASE, THROW THAT FILE TO ANY OF YOUR CLOUD BACKUPS. BACKUP IT TWICE (Use Telegram saved messages, for example)

7) Disconnect CH34A1 from PC, took clip off the chip

8) Open one of you dumped.bin in UEFITool. Search (CTRL+F), choose "Text" - H2OFormBrowser

9) UEFITool will find one GUID - 9E5DAEB4-4B91-4466-9EBE-81C7E4401E6D, named H2OFormBrowser. 

10) Right click on GUID name (9E5DAEB4-4B91-4466-9EBE-81C7E4401E6D) - "Extract as is", name it blah-blah.bin

11) Open Hex editor, open that blah-blah.bin

12) Open my provided file, choose "Compare". Please, note, that's not full bios, that's same module extracted for comparing to make your life easier.

13) Change all the things which is not similar to provided file. (You will make two 2 changes) (on latest bios)
Might work, if you just use the file provided, but i am not sure about that. 

14) Save your blah-blah.bin and close Hex editor

15) Open UEFITool, search for H2OFormBrowser again, right click on the same GUID, which you have extracted before - "Replace as is"

16) Save your dumped.bin 

17) Close UEFITool. Connect you clip again as mentioned above, connect CH34A1 to PC

18) Open CH34A1 software, choose "Erase", than choose "Blank", to check if chip is empty.

19) Open your dumped.bin in software, click on "Write" it will write and verify if buffer of file and bios chip is ok. 

20) If you have failed on any of steps with flashing - try connect clip, open software. 

21) Once your flashing process is done - close software, disconnect clip, disconnect CH34A1 from PC. 

22) Connect laptop battery back

23) Turn your laptop and smash F2 to boot into your unlocked bios. That's it. 
