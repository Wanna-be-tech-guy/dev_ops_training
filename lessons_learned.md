# Tech blog for the build and deployment of my DevOps Training Course

# Strange USB partititons
First issue I ran into (which I have never seen before, and still do not fully understand what was causing the issue, just the commands needed (from a UNIX system) to correct it) was strange partitioning of my USB stick.  
From my windows machine, it would show two drives (in this case, E: and F:) but neither were usable. It would say "Unsupported File system detected". From my Mac, I could not modify/erase the partiitons from the GUI Disk Utility.  
From the terminal, I could see the following partitions:  
/dev/disk4 (external, physical):  
```
   #:      TYPE NAME                                     SIZE       IDENTIFIER   
   0:      GUID_partition_scheme                        *31.0 GB    disk4  
   1:      Microsoft Basic Data                          247.8 KB   disk4s1  
   2:      EFI NO NAME                                   8.4 MB     disk4s2  
   3:      Apple_HFS PVE                                 1.4 GB     disk4s3  
   4:      Microsoft Basic Data                          307.2 KB   disk4s4  
                    (free space)                         29.6 GB    -  
```
Running the command `diskutil eraseDisk FAT32 USB /dev/disk4` corrected the issue, and allowed the drive to be reformated. 

# 
