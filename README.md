# Flippenheimer

Since I love my Flipper Zero, I want to maximize its utility in every possible way. I use the great 
akopachov's [Authenticator](https://github.com/akopachov/flipper-zero_authenticator) every day and [Mayhem v2](https://www.tindie.com/products/30630/) adds everything else I need... however, living in Norway, in close proximity to Russia, there's one essential addition that I believe should be considered: a Geiger Counter. 

I saw some great projects, but I need something compact, solid, that I plug and it just works. The beauty of this Geiger Counter is that it seamlessly integrates with the Flipper, drawing power from it, uses its display, and stores the data to it. It's the perfect symbiosis, an essential addition to my toolkit.

The design is heavily based on schematics using J305 for the flipper form factor.

<img src="https://github.com/eried/flipperzero-flippenheimer/assets/1091420/9768f67e-29cb-4539-8895-fa7d6a0b4f31" width="200">

## Compatible apps

*  https://github.com/nmrr/flipperzero-geigercounter (credits to [nmrr](https://github.com/nmrr))
*  https://github.com/nmrr/flipperzero-atomicdiceroller (credits to [nmrr](https://github.com/nmrr))

## BUY

You can [buy a kit or an assembled unit](https://www.tindie.com/products/31762/) from [Tindie](https://www.tindie.com/stores/eried/).

## DIY

### Option 1: Full DIY route
You can go full DIY with this Geiger Counter Kit https://s.click.aliexpress.com/e/_DkShdV9
and follow the instructions from https://github.com/nmrr/flipperzero-geigercounter

You only need some wires, pins and a 3.5mm headphone jack.

### Option 2: Flippenheimer PCB
If you got the prepopulated extra PCB, you need to solder few components:

| Location (PCB)         | Component                                       | Remarks                              |
|------------------------|-------------------------------------------------|---------------------------------------|
| (between F1 and F2/F3) | [J305 G-M Geiger Tube](https://s.click.aliexpress.com/e/_Dlvxtll)  | -     |
| F1, F2, F3             | [Fuse holder 5x20mm](https://s.click.aliexpress.com/e/_DCeZjmB) | Check the length of your tube and solder only 2 holders   |
|LS1|[Buzzer](https://s.click.aliexpress.com/e/_DCCKuQx) | - |
| IC1, IC2               | [555 DIP8 Timer](https://s.click.aliexpress.com/e/_DDvdlk7) | Make sure the pin 1 is in the correct orientation   |
| U80                    | [LM358 DIP8](https://s.click.aliexpress.com/e/_DE8xUTN) | Make sure the pin 1 is in the correct orientation |
| L1                     | [100 uH Inductor](https://s.click.aliexpress.com/e/_DBEpF0F) | - |
| L3                     | [10 mH Inductor](https://s.click.aliexpress.com/e/_DB6flLZ) | -  |
| Q1, Q3, Q4             | [2N3904 Transistor](https://s.click.aliexpress.com/e/_DediiMP) | Make sure is in the correct orientation |
| Q2                     | [MPSA42 Transistor](https://s.click.aliexpress.com/e/_DFNv1ZH) | Make sure is in the correct orientation|
| R100                   | [100 Ohm Potentiometer](https://s.click.aliexpress.com/e/_DC09Z4L) | Orientation does not matter |
| C6, C7, C20            | [10nF 1kV Capacitor](https://s.click.aliexpress.com/e/_DFvC8n9) | -   |
| C1, C2                 | [100uF 50V Capacitor](https://s.click.aliexpress.com/e/_DFhqFOR) | Make sure the positive leg (longer) is in the correct orientation|
| C21                    | [270pF 50V Capacitor](https://s.click.aliexpress.com/e/_Dc9j7ZN) | -  |
| D1, D2, D3             | [1N4937 Diode](https://s.click.aliexpress.com/e/_DFooson) | Make sure is in the correct orientation based on the band  |

#### Calibration

If you assembled the PCB, you need to calibrate it. First, check that the blue potentiometer is in the range of 50 ohms with a multimeter. Then carefully connect it to your Flipper Zero (there is high voltage parts, so be careful touching the board via the sides) and measure DC volts with your multimeter. Change the potentiometer until the DC voltage is around 175V
