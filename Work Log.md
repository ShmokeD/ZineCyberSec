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
