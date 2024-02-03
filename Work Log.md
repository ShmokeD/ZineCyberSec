29-01-2024 01:14
The virtualBox file seems to be broken. Opening up the ovf file shows that it seems to be searching for a "Stapler-disk1.vmdk"  file, which there isnt one.
I suspect thats because of the original project this one is created from. The fix seems to be just to edit the ovf file from "Stapler-disk1.vmdk"  to "ZinesWorstEnemy-disk1.vmdk".
This seems to work but Ill just confirm if thats intended or not

30-01-2024 00:22
Inital Nmap scans reveal multiple possible entry points; There is a mysql server, an ftp server, and a weird website
on port 12380. Inspecting the html of the page reveals a comment for someone named Zoe?. Moreover there is also some
data on port 666 which I havent been able to decipher.  

30-01-2024 00:30
I think im getting somewhere. I downloaded the gibberish using wget from port 666. Running file on that showed that 
it was a zip file. Unzipping which revealed a picture im quite perplexed by. I dont know what to do with it? Its 
titled message2.jpg. Wheres message1?

30-01-2024 16:29
I found out there was an open port 139 with a samba 4.3.9 running via nmap. Doing some research about
possible exploits led me to a is_known_pipename exploit. Using metasploit I was able to get into a VERY basic shell.
whoami returns root so thats a good sign i think.

30-01-2024 16:35
Well the shell was very useful. running passwd allowed me to set the password. moreover i can read the flag from here already.
~~~~~~~~~~<(Congratulations)>~~~~~~~~~~
                          .-'''''-.
                          |'-----'|
                          |-.....-|
                          |       |
                          |       |
         _,._             |       |
    __.o`   o`"-.         |       |
 .-O o `"-.o   O )_,._    |       |
( o   O  o )--.-"`O   o"-.`'-----'`
 '--------'  (   o  O    o)  
              `----------`
b6b545dc11b7a270f4bad23432190c75162c4a2b

30-01-2024 16:40
seems like the shell is a root shell but I cant see the output that the shell gives. using echo does not return an output.
I can only see like 1 line i think. I wont consider the project done until i can run simple bash.
My most easiest method seems to be a trick I learned a while ago to use netcat to listen on a specific port to create a reverse shell.
Learned from hak5.

30-01-2024 20:25
well the shell worked. I saw from sudo -l that I could execute binaries that I could execute bins from /usr/sbin. Looking into the directory,
visudo caught my eye. Learning more about visudo revealed that it opens some file in vi. I knew that i could escelate to a proper bash shell from there.
And i was right!!! I got a whole bash shell with output returning to me. I used this opportunity to execute the reverse shell command which gave me a backdoor into the system as well.

03-02-2024 23:08
This is the final log for the new project I was given. I opened the file using ida and gdb and other debugging/ decompiling tools. I understood
very little of the stuff at the start. But eventually started to understand how it goes down. The pseudocode helped by IDA helped a lot as well but confused me just as much. Unfortunately,
my findings were limited by my lack of understanding of what I was doing. I have renamed the functions as I saw fit and also started commenting the code. But two days is too small a time to 
find anything of meaning out of this.
