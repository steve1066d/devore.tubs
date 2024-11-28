# Custom Options for controlling a Softub

If you want more control over your hot tub than can be done with more standard approaches, here's some ideas of what others have done.  These are geared to electronics hobbyists.


### Arduino based solutions
Here's an example of someone that is using a custom Arudino replace the existing controller board. He integrates to the Softub using the existing temperature sensor and display
[https://www.reddit.com/r/esp32/comments/rscq6d/open_source_hot_tub_controller_project/]
[https://github.com/monroewilliams/softub/]

### Circuit Python based daughterboard
I made a custom daughterboard that fits between the control panel and the temp probe.  It’s a powerful solution, but isn’t something that you can buy off the shelf.  
It is an open source project that an electronics hobbyist could make. It also uses Home Assistant and  gives you lots of control in configuring your tub and controller.  
For example, I had things configured so when I held down the lights button on my Softub controller, it turned off the lights in my house. 
It also reports the temperature to Home Assistant as well.
[https://github.com/steve1066d/softub-wifi]
