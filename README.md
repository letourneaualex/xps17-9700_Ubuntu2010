# xps17-9700_Ubuntu2010
My journey into setting up my XPS 17 with Ubuntu 20.10


Laptop specs:
Dell XPS 17 (9700)\n
64Gb RAM\n
i7 10875H\n
1Tb SSD\n
RTX 206\n
4k\n

Install:
Ubuntu 20.10 single-boot - I thought 20.10 was a better option due the the newer kernel looking at issues other people had
LVM with encryption

Results:
- It took me many (4-5) attempts to be able to install the OS, the process failed both during and after the the OS install. Then I created the partitions beforehand and then was able to finish the install. I chose the minimal, no update and no 3rd party stuff to make it quicker and I also though there was less chance of trying to install drivers that aren't supported, but looking at the installation details maybe the normal install would've been faster as I think it loaded everything from the normal install and then removed everything. Anyway now it works well so I'm not going to dig more into this.

- The first few reboots I got and error with cups-browsed, but it stopped happening by itself after a few reboots.

- Configure Gestures using this process: https://medium.com/@kaigo/mac-like-gestures-on-ubuntu-20-04-dell-xps-15-7ea6e3be7f76 and it works well

- GPU seems to work well on Intel and NVidia profiles, but doesn't seem to switch properly when I set it to On-Demand - more investigation needed

- I'm realizing that the screen max refresh rate seems to be 60 no matter which resolution I chose which is weird because I bought this to replace my XPS 9570 which had a refresh rate of 120 for 2k and under. I never thought to check that before buying it as I thought for sure it would have at least the same refresh rate as my 2 years old xps 15, especially considering the RTX GPU, maybe it's a config issue - more investigation needed
      alex@alex-XPS-17-9700:~$ xrandr
      Screen 0: minimum 8 x 8, current 2560 x 1600, maximum 32767 x 32767
      DP-0 disconnected (normal left inverted right x axis y axis)
      DP-1 disconnected (normal left inverted right x axis y axis)
      DP-2 disconnected (normal left inverted right x axis y axis)
      DP-3 disconnected (normal left inverted right x axis y axis)
      eDP-1-1 connected primary 2560x1600+0+0 (normal left inverted right x axis y axis) 366mm x 229mm
         3840x2400     59.99 +  48.00  
         3840x2160     60.00    60.01    59.98    59.97  
         3200x1800     59.96    59.94  
         2880x1620     59.96    59.97  
         2560x1600     59.99    59.97* 
         2560x1440     59.99    59.99    59.96    59.95  
         2048x1536     60.00  
         1920x1440     60.00  
         1856x1392     60.01  
         1792x1344     60.01  
         2048x1152     59.99    59.98    59.90    59.91  
         1920x1200     59.88    59.95  
         1920x1080     60.01    59.97    59.96    59.93

- Sound does not work on speakers and headphone jack as I anticipated with what I read before buying it, works well on Bluetooth - Issue fixed using this process: https://km.kkrach.de/p_dell_xps_17_9700/ (however there's a typo in the commands, you're looking at sof-firmware-1.6-1 , not sof-firmware-1.6-2, also the wget command didn't work so I downloaded it straight from the website)
