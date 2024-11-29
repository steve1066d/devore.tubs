# Using a Sonoff Elite
A Sonoff Elite is used in much the same way as a Shelly device. Because it 
requires a separate AC power connection, and it bigger, it is a bit more complicated
to install.

### Installation Instructions:
[https://itead.cc/product/sonoff-th-elite-smart-temperature-and-humidity-monitoring-switch/ref/3/](https://itead.cc/product/sonoff-th-elite-smart-temperature-and-humidity-monitoring-switch/ref/3/)

Additional Requirements:
- A waterproof case for the Sonoff 
 A power cord for the Sonoff
- Cable glands to route cables through the control panel enclosure.
- A RJ9 telephone cable (like the following): (Note that it is smaller than a 
regular phone plug).
[https://www.digikey.com/en/products/detail/assmann-wsw-components/AT-S-26-4-4-B-7-OE/1972678](https://www.digikey.com/en/products/detail/assmann-wsw-components/AT-S-26-4-4-B-7-OE/1972678)
- A cable of 2 conductors. (24-28 AWG).

### Installation:
See the diagram:
[https://imgur.com/W8PoOOU](https://imgur.com/W8PoOOU)

    Adapter    RJ9
    VCC        4 (VCC)
    Data       3 (Signal)
    GND        1 (Ground)

The Dry contacts on the Sonoff COM and NO should be attached to Input and GND2
using the 2-conductor cable. (It doesn't matter which wire goes where).

You will need to route the wires through the control panel box.  Make sure
that you feed the cables through a cable gland (nut).  

There are two options for powering the Sonoff. Either use a separate AC plug, 
or else tie into the pump's power.  If you go the second route, that it would 
require drilling another hole in the steel cage for the Sonoff power cord.  Use
another cable gland for this cable.

The unit itself should be either installed outside of the Hydromate or 
possibly on top of the of the control panel enclosure.

### Alternate instructions for using a Shelly without the Wi-Fi adapter
It is possible to control the Softub without the adapter board, if you don't require returning the temperature from the Softub.

To install this, you don't need the RJ9 cable, but just use the 2 conductor cable, and install it on pins 5 and 8 on J9. It doesn't matter which wire goes to which pin 
To attach to the post, one option is to use [female jumper wire](https://www.amazon.com/Fielect-Female-Breadboard-Jumper-2-54mm/dp/B0819PX1GY) with one side cut off, and attached to the cable with Wago nuts.

The cable attaches to these posts:
![assets/sonoff-direct.jpg]
