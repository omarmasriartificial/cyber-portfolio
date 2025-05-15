## Reclaiming 10GB by Removing Leftover VirtualBox Disk Files
### Overview
While experimenting with virtualbox, i noticed 10gb of my ssd was missing after deleting the vm. Here is how i diagnosed the issue and recovered the space by manually locating and removing a hidden .vdi file.
### The Problem
After deleting my virtualbox vm, i expected all associated files to be removed. but i noticed my ssd still had 10gb missing. Here what was initially allocated to the vm: **10gb virtual disk**, **2gb ram**, **2 cpu**

### Investigation Process
1. **Checked the usual vm folders:**

   . C:\users\username\virtualbox vms
   
   . found nothing relevant

2. **Installed windirstat to analyze disk space:**

   . Downloaded from https://windirstat.net

   . scanned the entire C: drive

3. **Found a large .vdi file**

   . The file was buried in a hidden location

### Solution

1. Enabled **hidden items** in file explorer.
  
2. Navigated to the path shown in windirstat.

 3. Manually deleted the .vdi file

 4. Emptied the recycle bin

 5. Rebooted the system to see the freed up space

### Lessons Learned

. Deleting a vm does not always delete its virtual disk.

. Tools like windirstat are essential for investigating unexplained disk usage.

. File explorer does not always show you everything - hidden files can be space eaters.


      
