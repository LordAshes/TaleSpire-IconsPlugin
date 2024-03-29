# Icons Plugin

This unofficial TaleSpire plugin is for toggling up to 3 icons on each mini's base.
Icons are chosen from among multiple icons from a GUI menu. 

Demo: https://youtu.be/0XN0IkVIXL4

![Preview](https://i.imgur.com/Pp9lMx2.png)

This plugin, like all others, is free but if you want to donate, use: http://LordAshes.ca/TalespireDonate/Donate.php

## Change Log

```
2.2.0: Added option for up to 12 icons above the head instead of a max 3 on the base
2.1.1: Added diagnostic log level configuration to minimize log entries when not needed
2.1.1: Improved board loading process
2.1.0: Bugfix for icons in fly mode
2.1.0: Reworked code to simplify it and use Asset Data Plugin instead of Stat Messaging
2.0.0: Fix after BR HF Integration update
1.6.0: Fixed bug with icons in fly mode
1.6.0: Fixed bug with disabled icon packs
1.6.0: Improved sizing for larger base creatures
1.6.0: Improved startup
1.5.0: Icons are deleted when mini is deleted
1.5.0: Icons are available to GM and owner only
1.4.0: Corrected compatibility after TS update
1.3.1: Corrected ThunderStore dependencies (no plugin change)
1.3.0: Uses FileAccessPlugin so that icons do not need to be moved to the TaleSpire_CustomData folder anymore
1.2.3: Trying to get Thuderstore to display preview correctly
1.2.2: Trying to get Thuderstore to display preview correctly
1.2.1: Trying to get Thuderstore to display preview correctly
1.2.0: Added access to icons from radial menu using the Info main menu option and then the icons sub-menu option
1.2.0: Keyboard access uses full size line menu for icon selection. Radial menu uses radial sub-menu
1.1.0: Icons now scale with creature size
1.0.3: Fixed issue with moving the icons to a sub-folder
1.0.2: Plugin now appears on the TaleSpire main page
1.0.2: Moved icons to sub-folder to not conflict with Radial Menu icons
1.0.1: Fixed dependency requirement
1.0.0: Initial release
```

## Install

Install using R2ModMan or similar.

## Usage

Press the shortcut key to activate the Ioncs menu (Left CTRL + I by default but can be changed in R2ModMan) or use Info | Icons Radial
Menu selection. This brings up the Icons menu in the middle of the screen or as a circle if using the Radial UI.
Click an icon to toggle it. If that icon is not already present on the base, it will be added. If the icon was already present on the
base, it will be removed.

### Automatic Rotation

The positio of the icons is synchronized with the corresponding based in a gyroscopic way. When the mini sways diagonally when moving
the icons will not sway keeping the icons level. In addition the icons automatically rotate so that they are always facing the user
regardless of which direction the mini is facing or the direction that the camera is facing.

However, see Performance Modes below.

### The Power Of Three

Up to three icons can be displayed on each base. However, the system will actually remember more and display one of the missing ones
when a displayed icon is toggled off. However, practical uses should be limited to three icons so that all active icons can be seen.

### Stealth Mode

The plugin synchronizes the icons with the mini's stealth mode.

### Performance Modes

The plugin supports two plugin modes: Low Performance (default) and High Performance. The low performance mode has some limitations
but it is less stressful on the CPU and thus ideal for lower power devices. The high performance mode overcomes the limitations of
low performance mode but places a greater stress on the CPU and thus is ideal for more powerful devices.

The Performance Mode can be switched by going into the R2ModMan configuration for the Icons Plugin. Under the Settings section there
should be a configuration for the performance setting.

#### Low Performanmce Mode

In this mode, only the selected mini is updated in terms of position and the rotation angle of the icons in relation to the user.
In addition, any updates done by other clients are updated when the corresponding mini is dropped. This means it is possible to
see the base and the icons separate for a short duration when a non-local user has started to move a mini but has not dropped it
yet. Once the mini is dropped the icons will re-synchronize.

Since locally only the selected mini is being updated for icon angles, it is possible to rotate the screen so that the icons on
other mini become hidden. However, as soon as any of these minis are selected their icons will turn to face the user.

Another limitation of this mode is that, since minis only update when they are selected, when the board loads with a mini that
has icons, the mini needs to be pick up before the icons beome visible.

This mode performs a lot less work in the update cycle and thus is ideal for devices which are less powerful.

#### High Performanmce Mode

In this mode, all minis are constantly updated for position and rotation angle. Thus the icons on all minis face the user at all
time regardless of which mini is selected and there is no delay in updated.

In this mode, the icons are auotmatically hidden when the mini enters stealth more and automatically displayed when the mini exits
stealth mode.

However, this adds more complexity to the update cycle and this is more suitable for more powerful devices. It should be noted that
clients can mix and match the performance mode and the plugin can handle this. Clients using the high performance mode will get those
benefits while clients using the low performance mode will have the noted limitations.

## Custom Icons

To add, remove or modify the available icons, place 64 pixels x 64 pixel PNG files into the following directory:

D:\Steam\steamapps\common\TaleSpire\TaleSpire_CustomData\Images\Icons

The icons must be 64 pixels wide by 64 pixles high in order to be properly displayed in the menu and scaled  properly on the base.
The file name should be short (typically single word) name that prepresents the icon. While the name does not appear anywhere visually
it is used in the logs for trouble shooting purpose.

The files can make use of PNG alpha to make parts of the icon transparent or semi-transparent.


 
