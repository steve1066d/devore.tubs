# Replacement Softub firmware manual

This replacement firmware for the Softub works like the Softub provided
one, with a few enhancements.  Note that this product is not affiliated with 
Softub.  Softub and HydroMate are registered trademarks of Softub, Inc.

This firmware can be used with all digital boards.

### Features

The following are the differences and enhancements of this firmware over 
the stock firmware provided by Softub.

If the temperature is set, it will keep the set temp even if power is lost. 
The stock Softub firmware would revert to 100F (38C).

When power is first provided, the tub will show its set point for 5 seconds,
and then show the standard "P" (or the tub temperature if so configured), and
provides a simple way to see that this superior firmware is installed.

To quickly move the set temperature up or down hold down the button for 2 
seconds, and it will start repeating.  Lift up when the desired set temperature
is reached.

If a tub is running and the jets button is pressed, the tub will stop for 20 
minutes, even if it is heating (The stock program only will stop if it isn't 
heating. After the 20 minutes, it will start again, if it is cool enough to call
for heat.  However, if the ozone generator is running, the jets button will 
first stop the ozone, so if that is the case, and you want to stop the jets,
press the jets button a second time.

The special programs (SP1, Economy and Overnight nodes), can be chosen by
holding down the buttons for 4 seconds instead of 10 seconds the stock one
requires.  Also, you can enter SP1 without first setting the temperature to 104.  
The Economy and Overnight modes work fine even if the tub isn't up to 
temperature when they are set. When the Economy is exited (by holding down the
down and light buttons), The "24" will blink twice to indicate it is turned off.
Likewise holding down the down, light, and jets button will turn off the 
overnight mode, blinking "12" twice.

Once a temperature or special mode is selected, it will keep the setting even
if the tub loses power. So, if the tub is set to 102, instead of returning back
to 100, it will retain the temperature of 102. However, because the board 
doesn't keep time when it is off, it may run at odd times if the overnight or 
economy mode is selected when power is lost. If that happens, reselect the 
special mode.

Holding down the light button for 2 seconds will start the jets.  (Useful if
your jets button is broken).

Holding down the Light and Jets button for 4 seconds will display some diagnostic
information. It shows these values:
1. The version of the firmware (currently 1.05)
2. The number of days the Softub has been running without a power interruption 
   or reset.
3. The temperature of the microcontroller, in Celsius.  Note:  this isn't 
   calibrated, so it can be off by a large degree.
4. The temperature probe in tenths of a degree.  This is the unadjusted value.
   If the temperature is 100 or over, the value shown will be the temp minus 100.
5. The voltage of the power supply.  If the voltage drops below 97v
   the system will fail with the IPS error. If IPS is disabled, this is not 
   shown. The maximum voltage that will be displayed is 117v, even if the 
   voltage is higher.  For 220v systems, double the values given.

### Wi-Fi

Wi-Fi control of your Softub can be added with a simple add-on board that 
integrates with either a Shelly Uni or Sonoff Elite.  The Wi-Fi integration works 
along side the control panel, and keeps all the safety and functionality of the 
control panel.  See the separate Wi-Fi directions for details.

### The Improved program mode.

In this mode, the temperature is displayed in a more natural way.  Instead of
showing a P when the tub is off, it shows an estimate of the actual tub 
temperature.  Also, when the tub is running, it will show better estimate of the
temperature. The stock firmware essentially just showed the temperature probe
temperature of the Hydromate instead of trying to calculate the tub temp.

Also, if it sees the temperature is starting to drop, it will call for heat
so the tub keeps running. The tub would have to get quite cool before calling
for heat with the stock firmware.

Finally, instead of having to use the special mode to set the temperature to 
105 or 106, you can set it directly.
 
To enter the Improved mode, hold the up and down buttons together for 4 seconds.
The display will flash "P", indicating that the P display is disabled.

To return to the standard mode, repeat the operation by holding down the up and
down buttons again, until "P" is displayed.

### Errors:
IPS will reset automatically if the voltage corrects itself (similar to the 
stock board).  P01 can be reset by pressing any button.

