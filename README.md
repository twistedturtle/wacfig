# Wacfig

Simple software for configuring Wacom graphics tablets on Linux distros. Currently only tested with Bamboo One CTF-430 and Manjaro, will likely need some work for other tablets. Create an issue if you have a tablet you want supported.

The command allows you to change the config temporarily, and to save it to a config file in ` ~/.config/wacfig`.

To apply the configuration permanently, there's a systemd service file which is triggered at boot, and a udev rule file which triggers when you plug the device(s) in.



options:
  -h, --help            show this help message and exit
  -dbg, --debug         Print debugging info. Limited and only useful for dev, if that.
  --verbose, -v
  -l, --list            List all devices with index for use with --device.
  -d DEVICE, --device DEVICE
                        Specify device, indexed from 0. Only needed if you have more than one. If omitted and there are multiple the first device found will be used.
  -s, --setup           Apply the current configuration from file. Otherwise detect tablets and create a config file with the current config. Will process all tablets unless --device is specified.
  -m [MONITOR], --monitor [MONITOR]
                        Set which monitor to use. A number corresponding to the xrandr order, starts from 0. If no number it will cycle through the available monitors.
  -b BUTTON BUTTON, --button BUTTON BUTTON
                        Set what a button does.
  -p PRESSURE_CURVE PRESSURE_CURVE PRESSURE_CURVE PRESSURE_CURVE, --pressure-curve PRESSURE_CURVE PRESSURE_CURVE PRESSURE_CURVE PRESSURE_CURVE
                        Set the pressure curve.
  --save                Save the current config to the config file.
  -a ASPECT, --aspect ASPECT
                        Adjust the aspect ratio using either by limiting width or height (as on wacom page arch wiki). Takes one of: height, width (not as good), reset.
  -r ROTATE, --rotate ROTATE
                        Set rotation in 90 degree increments. Accepts one of: none, half, cw, ccw.


### Install

Arch based distros - Download the PKGBUILD, put it in a directory and run `makepkg -si`. I may upload the PKGBUILD to the AUR in future.


wacfig -> /usr/local/bin/
wacfig.service -> /usr/lib/systemd/user/
95-wacom.rules -> /etc/udev/rules.d/

`wacfig -s`


### Questions/Bugs/Issues/Feature requests etc
If you have any questions or feedback etc please open an issue.
