# thinkpad-l390-yoga-scripts

A simple set of scripts to control screen rotation and tablet mode for the Lenovo L390 Yoga, based on [thinkpad-l380-yoga-scripts by ffejery](https://github.com/ffejery/thinkpad-l380-yoga-scripts) and [linux_detect_tablet_mode by alesguzik](https://github.com/alesguzik/linux_detect_tablet_mode). 

## What it does

When the screen hinges are opened more than 180 degrees, automatic rotation of the screen is started, keyboard, touchpad and trackpoint are disabled. When hinges are turned back, automatic rotation is disabled, and keyboard, touchpad and trackpoint are enabled again. 

## How to use

Build and install the package, it has been packaged for Arch Linux. See PKGBUILD for details. 

Default config is done via ~/.config/watch-tablet.yml. You need to open the file and replace `YOURUSERNAME` with your actual user name for the package to work. 

Start the program with `/opt/thinkpad-l390-yoga-scripts/watch-tablet`. If you want it to autostart you can put the following line in your `.xinitrc` or `.xprofile`: 

```
/opt/thinkpad-l390-yoga-scripts/watch-tablet &
```

If you run `startx` manually, it should be in `.xinitrc`. If you use SDDM (like I do) it should be in `.xprofile`. Other DEs/WMs might have other solutions. 

I have only tested this on Arch Linux with Xmonad, using SDDM to start X. Other applications might work but have not been tested. 
