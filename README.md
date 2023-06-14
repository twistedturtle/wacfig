# Wacfig

A wrapper for xsetwacom, for easier configuring of Wacom graphics tablets on Linux distros. Currently only tested with Bamboo One CTF-430 and Manjaro, will likely need some work for other tablets. Create an issue if you have a tablet you want supported.

The command allows you to change the config temporarily, and to save it to a config file in ` ~/.config/wacfig`.

To apply the configuration permanently, there's a systemd service file which is triggered at boot, and a udev rule file which triggers when you plug the device(s) in.

I don't use this much and I haven't seen the code in a while. Hopefully it still works. I'll check it out properly soon, but in the mean time if you encounter any problems please open an issue.

### options:</br>
  #### -h, --help 
  show this help message and exit</br>
  
  #### -dbg, --debug
  Print debugging info. Limited and only useful for dev, if that.</br>
  
  #### --verbose, -v</br>
  
  #### -l, --list
  List all devices with index for use with --device.</br>
  
  #### -d DEVICE, --device DEVICE</br>
                        
  Specify device, indexed from 0. Only needed if you have more than one. If omitted and there are multiple the first device found will be used.</br>
                        
  #### -s, --setup           
  Apply the current configuration from file. Otherwise detect tablets and create a config file with the current config. Will process all tablets unless --device is specified.</br>
  
  #### -m [MONITOR], --monitor [MONITOR]</br>
  Set which monitor to use. A number corresponding to the xrandr order, starts from 0. If no number it will cycle through the available monitors.</br>
                        
  #### -b BUTTON BUTTON, --button BUTTON BUTTON</br>
  Set what a button does.</br>
                        
  #### -p PRESSURE_CURVE PRESSURE_CURVE PRESSURE_CURVE PRESSURE_CURVE, --pressure-curve PRESSURE_CURVE PRESSURE_CURVE PRESSURE_CURVE PRESSURE_CURVE</br>
  Set the pressure curve.</br>
                        
  #### --save                
  Save the current config to the config file.</br>
  
  #### -a ASPECT, --aspect ASPECT</br>
  Adjust the aspect ratio using either by limiting width or height (as on wacom page arch wiki). Takes one of: height, width (not as good), reset.</br>
                        
  #### -r ROTATE, --rotate ROTATE</br>
  Set rotation in 90 degree increments. Accepts one of: none, half, cw, ccw.</br>

https://wiki.archlinux.org/title/Graphics_tablet</br>
https://man.archlinux.org/man/xsetwacom.1

### Install

#### Arch based distros 
Download the PKGBUILD, put it in a directory and run `makepkg -si`. I may upload the PKGBUILD to the AUR in future.


#### For everyone else
Hopefully I'll update this section to be more useful in future. For now:

wacfig -> /usr/local/bin/</br>
wacfig.service -> /usr/lib/systemd/user/</br>
95-wacom.rules -> /etc/udev/rules.d/</br>

`wacfig -s`


### Questions/Bugs/Issues/Feature requests etc
If you have any questions or feedback etc please open an issue.
