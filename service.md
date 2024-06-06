## Service Mode
It is possible to go into a special service mode to change various settings
of this firmware. Please be sure you understand the ramifications of these
settings before changing anything.  It is not expected that the user of the 
tub will need to modify these settings, but they are documented in case there
is some special need to change something.

To enter the service mode, press all 4 buttons for 4 seconds. You should see
PP0 on the display.  If you have issues with the system not recognizing 4 
buttons, hold down the lights button, then press each of the other buttons.  
After you have pressed the last button, the service mode should start after 4 
seconds.  Then release the lights button.

Use the up and down arrows to choose the setting you wish to set.  Use the 
Lights button to select the value to change. Pressing jets will save the 
settings return to the normal controls.

After pressing the lights button, it will show the current setting.  Use the 
lights button to move to the next digit.  The digit you are at will flash.  If 
the hundreds place is selected and has a 0 it will not flash because the 
display cannot show a 0 in that position. To save the value, press 
the jets button. If you don't respond within 5 seconds, the system
will go back to the previous menu without saving any changes.

Valid values are between 0 and 255. There's no error checking so 
be careful what you set things to and verify the settings do what you are
expecting. If you want to revert to default settings, set the default 
temperature (PP0) to "255".  On next restart it will replace all settings with
defaults.

While in the service mode you can press the up and down buttons to reset the 
Softub. Doing so will not save any changes you have made.

#### PP0: Default temperature.  
If you want the system to be set to a different temperature on startup, change 
this.  Though normally this is changed automatically when the setting changes.

#### PP1: Probe offset. 
This is tenths of a degree to offset the probe setting, with 10.0 as the base. 
So, a setting of "9.0" will cause the temperature to be reported 1 degree colder.
A setting of 12.0 will be 2 degrees warmer.  Values under 10.0 cause pool 
temps to get hotter because it is adjusted to a lower temperature.

#### PP2 Minimum temp allowed.  
The minimum temperature allowed to be set.  Make sure it is safely above 
freezing.

#### PP3 Maximum allowed temp.  
The maximum allowed temp.  The default 104F (40C) is the recommended maximum 
temperature for hot tubs. This adjustment is provided if you want to lower the 
maximum if you have children, or are otherwise concerned about the maximum 
temperature. Increasing this is not recommended for safety reasons. Also, 
setting this too high will cause the board's high limit safety feature to 
activate, disabling the pump.

#### PP4 Pump on value
Once the tub is up to temp, the system waits until the temp probe goes down 
this many degrees F (or half degrees C) before calling for heat again. The 
default is 4 but if you increase it, the pump will run less often (but for 
longer).  As power cycles increase the wear on the pump, it may be helpful to 
adjust this.  It is important to note that the temp probe is inside the 
HydroMate, so you may find that a large deadband only causes a small fluctuation 
in tub temperature.

#### PP5 Pump off value
If the pump is heating, if the temperature is this degrees F over (or half 
degrees C), then the pump will shut off.  The default is 2. 

#### PP6 Operational flags
To use this, add up the numbers and configure that value. If you want to 
use Fahrenheit, disable P and disable IPS, you would enter 11 (1 + 2 + 8).  
Note that generally the flags disable something, so you would set it to "1" to 
disable the feature.

1 = Use Fahrenheit.  If this is not set it will display the temperature in
Celsius. The default is the setting of JP2 on the board.  If the pads are 
jumpered the default is Celsius. If you change this flag, it will replace the 
maximum, minimum and default temps to default values.

2 = Disable P.  Normally the controller will use the stock rules of displaying P 
when the pump is off or just started.  If this flag is set, it will instead show
the temperature of the probe in the HydroMate. With the pump not running it
won't be as accurate as when the pump is running, but will still give an 
indication of the tub temperature.

4 = Disable Ozone.  Softub has an optional ozone generator that is run 
periodically to limit the chemical use.  However, they tend to fail, and 
generally are not replaced. If you are not using or do not wish to use the 
ozone generator, set this flag.

8 = Disable IPS.  The board monitors the voltage is sufficient to not 
cause damage to the pump. It fires if the voltage drops to 96.5 volts on a 120v
system (or probably around 177 v on a 220 circuit).  To disable this test, set 
this flag. However, if there is insufficient power for the microcontroller, 
it could still respond with an IPS warning.

16 = Disable P01:  If the tub has been heating for 4 hours without a 1 degree 
temperature increase, the system will stop, and display a P01 error.  If you 
would rather it keep going in those situations, set this flag.

32 = Disable SP1: 
The controller allows you to go up to 2 degrees F higher (or 1 degree C) than 
the maximum configured in PP1, by using the "special temperature" controls that 
the stock Softub board uses. If you wish to disable this for safety, or if you 
changed the maximum to where you want it in PP1, set this flag.

64 = Disable Smart Temperatures:
The software tries to estimate the tub temperature taking into account the set
points and heat status.  If instead you want to display the raw temperature of 
the probe (similar to what the stock firmware does), use this flag. 

128 = Encode status as humidity reading.
See the Wi-Fi guide for details

#### PP7  Additional service flags.
1 = Disable Save settings:
The controller will normally save the selected temperature and the mode the 
tub is running in so it will keep that setting if power is lost.  If you rather
it instead always return to the saved defaults, set this flag.

2 = Disable service menu.  This could be useful if you have the settings you want 
and you don't want anyone to muck with them.  If this is disabled, holding the 
four buttons simply causes the controller to restart. However, if you set this
flag, it means that you won't be able to change any of these PP settings without 
opening up the HydroMate. Temporarily adding a jumper across JP3 on the board on 
startup will reset the configuration to the default and reenable this menu.

4 = Disable wait for service menu.
If this is enabled, then pressing the 4 buttons will immediately bring up the
service menu instead of requiring a 4 second hold.

8 = Disable Decimal
If this is enabled, then the board will not try to send out a decimal point.
Decimal points are only used for Celsius, and the PP1 menu, and version number. 
The early 2001 top units (with a + and - instead of an up and down arrows) 
cannot display decimal points).

16 = Stock Settings
If this is enabled, the board will more closely follow the stock C-2013 firmware

32 = Disable proactive heat
If the firmware notices the temperature is going down with the heat on, it will 
turn the heat mode on even if it hasn't hit the setpoint yet.

64 = Enable tenth degree
Normally the board reports full degrees (or half degree Centigrade).  To instead 
show the temperature to the tenth of a degree enable this.  Note, if the 
temperature is 100 or over, it can't show the tenths, and instead will end the 
value with a decimal point if it is .5 or over. So 100.2 will show as "100" and 
100.6 will show as "100."

#### PP8 Mode.  This does not need to be edited, as it can be changed with the 
documented commands
00 = Startup in normal mode
01 = Startup in economy mode
02 = Startup in overnight mode

#### PP9 Wi-Fi mode.  See Wi-Fi notes for details

#### P10 Microcontroller temperature adjustment.
This can be used to adjust the temperature reported in the diagnostic info to 
more accurately reflect degrees Celsius.  Decrease this value if the 
temperature is to high, increase it if it is too low.  The units are degrees 
Celsius.

#### Alternate Buttons

If a top panel button or buttons fail, it is possible to add a normally open 
push button to the jumper pads on the board.  To do this you would need to
solder a pair of wires on the jumper pads, then route the wires for the 
pushbutton out of the enclosure.  If you go this route, make sure you have a 
waterproof cable nut to protect the enclosure from getting wet and you route the 
cable so that it has a dip below the pump to make sure water doesn't work its 
way into the control panel box. While it would be better to replace the control 
panel, this is an option for someone confident on their installation skills.  You 
can either replace all the buttons or just the broken buttons.  Here's the 
connection placements:

    JP3: Lights
    JP4: Jets
    JP5: Up
    JP6: Down

