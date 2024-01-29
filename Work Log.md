9-01-2024 01:14
The virtualBox file seems to be broken. Opening up the ovf file shows that it seems to be searching for a "Stapler-disk1.vmdk"  file, which there isnt one.
I suspect thats because of the original project this one is created from. The fix seems to be just to edit the ovf file from "Stapler-disk1.vmdk"  to "ZinesWorstEnemy-disk1.vmdk".
This seems to work but Ill just confirm if thats intended or not