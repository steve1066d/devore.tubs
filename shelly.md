### Installation Instructions for A Shelly Plus Uni
[https://www.amazon.com/dp/B0CQD1Z2K8](https://www.amazon.com/dp/B0CQD1Z2K8)

Pins 4-7 on the Shelly need to be connected (the others are not used)

Attach the enclosed cable from the Shelly to the socket on the adapter board.

The OUT1 black wires should be attached to the following (It doesn't matter 
which black wire goes to which connection)

- OUT1: In
- OUT1: GND2

Follow the directions from Shelly to get it up and running. It is recommended to 
temporarily power it from the usb connector before installing it in the tub. You
should be able to turn it on and off the from the Shelly app before installing
it in the Hydromate.

When installing the Shelly, wrap it with tape to help ensure it doesn't rub against any electrical components.  
Consider using zip ties to secure the Shelly.

### Notes
The Shelly recommends running when the ambient temperature is no more than 
104F.  However, because we aren't driving current through it it should heat 
up less and be okay in the Hydromate.  It will shut off if it reaches 95C (203F).
If that happens you should look at changing the location of the Shelly.  You
may also put in a waterproof case outside the Hydromate, or on top of the box
housing the control panel.
See the following for details on how the Shelly handles high temperatures:
[https://support.shelly.cloud/en/support/solutions/articles/103000221554-shelly-devices-operating-temperature](https://support.shelly.cloud/en/support/solutions/articles/103000221554-shelly-devices-operating-temperature)


#### Additional Notes for C-2001 Installation

This board uses a power supply that puts out more heat than other boards, so
it may get too hot for the Shelly to be inside of the control box or powered from the board.
This unit should be installed outside the board enclosure. Possible locations are on top of the enclosure, or 
even outside the Hydromate in a waterproof box. To extend the wires, Wago connectors can be 
used, along with wire (22 to 28 AWG). [https://www.amazon.com/dp/B07CNKLZPQ](https://www.amazon.com/dp/B07CNKLZPQ). Instead of using 
the socket and cable, you can use the screw terminal to connect the wires:

- Pin 4 (Yellow): VCC
- Pin 5 (Blue):   Data
- Pin 7 (Green):  GND

Pin 6 (5V) should only be hooked up if you are powering the Shelly from the board (which isn't recommended for the C-2001 boards.).

