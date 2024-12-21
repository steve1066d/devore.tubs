# Steve Devore's Softub improved firmware

This project addresses many of the problems and limitations of the existing Softub control board functionality. It does this by replacing the microcontroller
on the chip with another one.  You can either upgrade your existing controller board or get a refurbished board with this new program.
Note, this is not affiliated with Softub Spas.

### Features:
- Can be added to any board (C-2001, C-2003, C-2006, and C-2013), giving new
functionally to older boards.

- It is a drop in replacement for existing boards.  There are no other changes needed.

- All existing functionality of the C-2013 board is provided, with over-temp 
protection, IPS and P01 errors, special temp mode, and economy and overnight
modes. The safety of the original design is kept.
- It will keep the set temperature if power is lost, so you can put the tub on a 
timer.

- The maximum temperature is configurable, so you aren't limited to 104F (40C).
Also, you can adjust the temperature to match the real tub temperature, if 
desired.

- You can hold down the up or down arrows to rapidly change the tub temperature.

- You can pause the pump for 20 minutes, even if it is calling for heat by 
pressing the jets button. You can have silence when you soak if you so desire.

- It can optionally display the tub temperature even when the pump is off, and can 
provide a more accurate estimate of the actual tub temperature compared to the 
stock firmware.  

- It can be monitored and controlled with Wi-Fi using a Sonoff Elite, or a Shelly 
Uni Plus, along with an optional Wi-Fi adapter board.  It works in conjunction
with the existing control panel, keeping the safety and functionality
of the system intact.

- If your control panel has buttons that don't work, you can add normal pushbuttons to control
your hot tub.

- It can work with replacement power supplies, so if you've been told the board can't be repaired, it likely can be now. 
  [Here is an example](assets/repaired.jpg)
  
- There is a service menu that lets you change many of the parameters, like changing from Fahrenheit to Celsius.

### Documentation
  
[User's Manual](manual.md)

[Service Manual](service.md)

Upgrading existing Softub boards would generally be done by a electronics professional.  These instructions are for upgrading a board:
[Installation Instructions](install.md)

[Wi-Fi integration](wifi.md)

### Ordering
Either order just the upgrade, or also [repair or refurbish your board](ordering.html)

