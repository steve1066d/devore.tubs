# Installation Instructions

This updated microprocessor is meant to be installed on a Softub controller 
board.  It is compatible with the C-2001, C-2003, C-2006, and C-2013 board 
revisions, both the European and US variants.  Its compatible with the 
current control panels, as well as the original control panel released with the 
2001 units.

The microcontroller is a PIC18F24Q10-E/SO.  The version and batch information 
are in the first 6 bytes of the User ID memory on the chip.

The EEPROM memory is used to store the settings documented in the service menu.  
PP0 is the first byte of EEPROM memory.  If that first byte is "FF" then it will
restore the settings to factory defaults the next time it is started.

The old style control panel (with the brown connector and + and - buttons 
instead of arrows) has a limitation in that it can't show decimal points and 
can't show "P".  Instead of a P it shows and upside-down P with a segment 
missing. However, besides those limitations it works fine.

The first time the board is powered up after installation the chip configures 
itself.

If JP2 is jumpered, the board will use Celsius.  Otherwise, it will use 
Fahrenheit.

If JP4 is jumpered, the 36v voltage check for IPS will be disabled.  This is 
useful for C-2001 boards since they don't support this. (If this is left enabled
on a C-2001 board it will cause an IPS on startup).  Also, this can be used if 
the board has been modified by replacing the AC to DC power circuit with a 
replacement 5V power converter.

After starting the first time, the jumpers are subsequently ignored, and instead
uses the configuration stored in EEPROM.

If JP3 is jumpered and powered, it will reset the chip back to defaults (and 
again will check the JP2 and JP4 jumpers).  To do this, power the board with JP3 
jumpered (you can also connect pins 2 and 8 on J9), and power the board. Power 
off the board, remove the jumper, make and restart it.  If the JP3 jumper is 
left on, it won't save any settings to EEPROM.

Some C-2013 boards do not have ground on Pin J9-8.  For those, it is recommended
to jumper JP2 to provide ground for the Wi-Fi adapter board. This needs to be 
done if there is not continuity between J9-8 and J2-3. Since that jumper is 
used to indicate a Celsius board, if Fahrenheit is desired, power up the board
before adding the jumper, or else the board will default to Celsius.
