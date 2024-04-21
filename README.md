# m5dial

ESPhome YAML files to use your M5 dial device.

I was really really happy when SmartWomo group User "Markus Gebert Deutschlad" sponsored me a M5 dial that I can tinker with.
It is meant to use this device in my camper to control all the smart things that I built in. Most with help of the great Womolin group users. It will control all the lights (using my self-developed smart 8channel or 2channel control module) and my Truma Combi heater. All using ESPhome that will connect to my Home Assistant (HA) instance running in my camper.

Based on work of Squall290586 & dgaust and heavily modified to suit my needs, like refactoring to use packages.
Please see this thread, where I took copied the initial yamls from - with pride ;-)
https://community.home-assistant.io/t/m5stack-dial-esp32-s3-smart-rotary-knob/623518/119 

Idea is to have specific display pages for HA objects that can be cycled thorugh.

In your main yaml you need to include the display.yaml first as this initializes the display, touchscreen and other necessary thigs.
Then you can add multiple pages in your preferred order which can switched by using the button on the M5 dial.

Whenever you include a page you can override certain configuration items by using vars:.
Please always state your entity id and choose a unique name variable for each page.

To save power, the backlight will be turned off after some time. Configurable in <>

At this moment in time there are the following pages available
# clock 
Shows the actual time. This page should only be included once. It can be selected by long-pressing the button from every other page.

# light
Enables you to control a light entity. Use the dial to control the brightness and touch the icon to toggle the light on or off.

# climate
Enables you to control a climate entity. Use the dial to set the desired temperature. The new set temperature will be sent to HA after a few seconds to prevent setting the temp after each step.
You have the possibility to use 4 preset buttons e.g. for "not at home", "sleep", "standard" and "boost".

# media player
Enables you to control your media player entity. Use the dial to set the volume and the touchscree to toggle play or pause.


# known issues
There are still many "bugs" that I need to eliminiate. Please be patient ;-)

- sometimes the display stays dark if the dial is powered on. It seems that you need to touch/dial/click to start the display timeout counter. After it reaches 0 and you touch it again, the display turns on.
- would also like to have the nice visual circle like in climate to show brightness or volume in other pages. But I didn't finde a way to make it a nice package to be reused.
- in my configuration the new brightness is not set correctly as it is updated from HA while trying to set a new value. But I think it is related to my personal setup using ZHA and deconz in parallel.
- poorly documented the files and their functionality

Please use issues or requests for further updates.
Or donate by buying me a coffee.

