# Flippenheimer

I love my Flipper Zero, I want to maximize its utility in every possible way. I use the great 
akopachov's [Authenticator](https://github.com/akopachov/flipper-zero_authenticator) every day and [Mayhem v2](https://www.tindie.com/products/30630/) adds everything else I need... however, living in Norway, in close proximity to Russia, there's one essential addition that I believe should be considered: a **Geiger Counter**. 

I saw some great approaches to this, but I need something that just works, no fiddling around. The beauty of this Geiger Counter is that it seamlessly integrates with the Flipper, drawing power from it, uses its display, and stores the data to it. It's the perfect symbiosis, an essential addition to my toolkit.

The design is heavily based on schematics using a J305 Geiger–Müller tube for the flipper form factor.

<img src="https://github.com/eried/flipperzero-flippenheimer/assets/1091420/7fcb22d8-ab54-4fef-bdee-1291296785e6" width="200">

## Compatible apps

### [Geiger counter](https://github.com/nmrr/flipperzero-geigercounter)

This app gives you a graph view with counts per second (instantaneous measure of the radioactivity) as CPS and per minute as CPM.

There is extra functionality to record, zoom, change units, etc.

![image](https://i.imgur.com/pR0H5AOt.png) ![image](https://i.imgur.com/DNJpODQt.png)

(credits to [nmrr](https://github.com/nmrr))

### [Atomic dice roller](https://github.com/nmrr/flipperzero-atomicdiceroller)
 
With this app you can get a really random dice based on the geiger counter. Make your decisions and board games extra exciting.

![image](https://i.imgur.com/Lg1I0Pxt.png) ![image](https://i.imgur.com/pC3x7yPt.png)

(credits to [nmrr](https://github.com/nmrr))

# Build or buy

## BUY

You can [buy a kit or an assembled unit](https://www.tindie.com/products/31762/) from [Tindie](https://www.tindie.com/stores/eried/).

## DIY

### Option 1: Full DIY route
You can go full DIY with a [Geiger Counter Kit](https://s.click.aliexpress.com/e/_oovR4M9) and follow the instructions from https://github.com/nmrr/flipperzero-geigercounter

You only need some wires, pins and a 3.5mm headphone jack.

### Option 2: Flippenheimer PCB
If you got the prepopulated extra PCB, you need to solder few components:

| Location (PCB)         | Component                                       | Remarks                              |
|------------------------|-------------------------------------------------|---------------------------------------|
| (between F1 and F2/F3) | [J305 G-M Geiger Tube](https://s.click.aliexpress.com/e/_c3DIOEm1)  | -     |
| F1, F2, F3             | [Fuse holder 5x20mm](https://s.click.aliexpress.com/e/_oFT81yF) | Check the length of your tube and solder only 2 holders   |
|LS1|[Buzzer](https://s.click.aliexpress.com/e/_onoI7pl) | You can try different versions of buzzers, some do the "clicky" sound (pasive), some do the "beepy" sound (active) |
| IC1, IC2               | [555 DIP8 Timer](https://s.click.aliexpress.com/e/_oEtT2YJ) | Make sure the pin 1 is in the correct orientation   |
| U80                    | [LM358 DIP8](https://s.click.aliexpress.com/e/_DE8xUTN) | Make sure the pin 1 is in the correct orientation |
| L1                     | [100 uH Inductor](https://s.click.aliexpress.com/e/_DBEpF0F) | - |
| L3                     | [10 mH Inductor](https://s.click.aliexpress.com/e/_ooLP9WX) | -  |
| Q3, Q4, Q5             | [2N3904 Transistor](https://s.click.aliexpress.com/e/_olyDjP1) | Make sure is in the correct orientation |
| Q2                     | [MPSA42 Transistor](https://s.click.aliexpress.com/e/_opuZVHd) | Make sure is in the correct orientation|
| R100                   | [100 Ohm Potentiometer](https://s.click.aliexpress.com/e/_c3pSHd6V) | Orientation does not matter |
| C6, C7, C20            | [10nF 1kV Capacitor](https://s.click.aliexpress.com/e/_oDL7Fgb) | -   |
| C1, C2                 | [100uF 25V Capacitor](https://s.click.aliexpress.com/e/_olwpVN5) | Make sure the positive leg (longer) is in the correct orientation|
| C21                    | [270pF 50V Capacitor](https://s.click.aliexpress.com/e/_oFtnLKJ) | -  |
| D1, D2, D3             | [1N4937 Diode](https://s.click.aliexpress.com/e/_oodGWzt) | Make sure is in the correct orientation based on the band  |
| (for calibration) | [50M ohm resistor](https://s.click.aliexpress.com/e/_c3Uzpcqh) | Any resistor kit will do, combine them in series to 50M ohm |
| (pin headers)       | [2.54mm angled pin headers](https://s.click.aliexpress.com/e/_okcglvh) | You need 10P and 8P, but you can cut them down to size, so 10P works for both |

#### Calibration

Only calibrate if you assembled the PCB. If it was pre-assembled, it is already calibrated. You need 50M ohm resistors and a multimeter. Check more details about the process [here](https://github.com/SensorsIot/Geiger-Counter-RadiationD-v1.1-CAJOE-/blob/master/En_Calibration_GMv1.1.pdf).

1) Keep the device disconnected from power. Remove the geiger tube if is installed

2) Adjust R100 to 50 ohms

3) Set the multimeter to VDC, highest range (i.e. 400V).

4) Connect GND to the multimeter (i.e. the left tube clamp)

5) Connect the positive tube clamp to the multimeter positive probe, using 50M ohm in resistors between them

6) Power the device and adjust R100 until your multimeter shows 57V (if is a 10M multimeter) or 6.5V (if is a 1M multimeter).

**The device is now calibrated**. Now you can place the geiger tube. You might add a dab of glue to hold the potentiomenter R100 in place.
