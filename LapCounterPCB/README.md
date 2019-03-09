# Lap Counter PCB collection

### lc_led
**IR sender LEDS and current limiting driver circuit**

lc_led_R1_V-drop.png - scope image recorded across R1. P-P voltage must be 4.4V

**LC_Power - power management board + 38kHz generator board**

Power Management Board (a):
- two battery inputs (lead acid or 18V Lithium Power tool battery
- automatic changeover between batteries
- display battery info on LCD
- connects to external buck/boost converter to provide 15.6V for LED boards
- provides POE injector for Ubiquity Bullet Access Point (unregulated)
the small board on this PCB contains the 38kHz pulse generator required to drive the LED boards.

38kHz Generator Board:
This board consists of a voltage regulator and ATtiny85 to generate the 38kHz signal (see LC_Power_38kHz.png) required to pulse the IR LED transmitter. The supply voltage is expected to be 15.6V.
The supply and 38kHz pulse are made available on 3 pin headers.


**LC_wemos - boards for Wemos based IR receiver**
