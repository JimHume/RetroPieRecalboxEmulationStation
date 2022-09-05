Note that when performing an apt update, the ini file will be overwritten for the emulator in most circumstances

To fix the controller not working as expected:
1. Edit the recalbox config file, adding `n64.configfile=dummy` or something nonexistent
  - This can be accomplished either through the "recalbox manager" (http://<pi ip address>/) or via text editor.
  - If doing this via text editor, the file should be located at `/recalbox/share/system/recalbox.conf`
2. Copy/paste the [DragonRise ini file](DragonRise.ini) into `/recalbox/share/system/configs/mupen64` renaming it to `InputAutoCfg.ini` 
3. Edit the `/recalbox/share/system/configs/mupen64/mupen64.cfg` file in a text editor (this part sucks). 
  - Find the `[Input-SDL-ControlX]` section(s) and edit them to match the `DragonRise.ini` file.
  - Rinse/repeat for all controllers if desired
  
The sample section from mupen64.cfg is:
```
[Input-SDL-Control1]

# Mupen64Plus SDL Input Plugin config parameter version number.  Please don't change this version number.
version = 2
# Controller configuration mode: 0=Fully Manual, 1=Auto with named SDL Device, 2=Fully automatic
mode = 2
# Specifies which joystick is bound to this controller: -1=No joystick, 0 or more= SDL Joystick number
device = 0
# SDL joystick name (or Keyboard)
name = "DragonRise Inc.   Generic   USB  Joystick  "
# Specifies whether this controller is 'plugged in' to the simulated N64
plugged = True
# Specifies which type of expansion pak is in the controller: 1=None, 2=Mem pak, 5=Rumble pak
plugin = "2"
# If True, then mouse buttons may be used with this controller
mouse = False
# Scaling factor for mouse movements.  For X, Y axes.
MouseSensitivity = "2.00,2.00"
# The minimum absolute value of the SDL analog joystick axis to move the N64 controller axis value from 0.  For X, Y axes.
AnalogDeadzone = "4096,4096"
# An absolute value of the SDL joystick axis >= AnalogPeak will saturate the N64 controller axis value (at 80).  For X, Y axes. For each axis, this must be greater than the corresponding AnalogDeadzone value
AnalogPeak = "32768,32768"
# Digital button configuration mappings
DPad R = "axis(5+)"
DPad L = "axis(5-)"
DPad D = "axis(6+)"
DPad U = "axis(6-)"
Start = "button(9)"
Z Trig = "button(7)"
B Button = "button(8)"
A Button = "button(6)"
C Button R = "button(1)"
C Button L = "button(3)"
C Button D = "button(2)"
C Button U = "button(0)"
R Trig = "button(5)"
L Trig = "button(4)"
Mempak switch = "key(109)"
Rumblepak switch = "key(114)"
# Analog axis configuration mappings
X Axis = "axis(0-,0+)"
Y Axis = "axis(1-,1+)"
