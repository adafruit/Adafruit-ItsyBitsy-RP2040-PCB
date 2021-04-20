## Adafruit ItsyBitsy RP2040 PCB

<a href="http://www.adafruit.com/products/4888"><img src="assets/4888.jpg?raw=true" width="500px"><br/>
Click here to purchase one from the Adafruit shop</a>

PCB files for the Adafruit ItsyBitsy RP2040.

Format is EagleCAD schematic and board layout
* https://www.adafruit.com/product/4888

### Description

A new chip means a new ItsyBitsy, and the Raspberry Pi RP2040 is no exception. When we saw this chip we thought "this chip is going to be awesome when we give it the ItsyBitsy teensy-weensy Treatment" and so we did! This Itsy' features the RP2040, and all niceties you know and love about the ItsyBitsy family.

What's smaller than a Feather but larger than a Trinket? It's an Adafruit ItsyBitsy RP2040 featuring the Raspberry Pi RP2040! Small, powerful, with a ultra fast dual Cortex M0+ processor running at 125 MHz - this microcontroller board is perfect when you want something very compact, with lots of horsepower and a bunch of pins. This Itsy has sports car speed, but SUV roominess with 8 MB of FLASH and 264KB of SRAM.

ItsyBitsy RP2040 is only 1.4" long by 0.7" wide, but has 6 power pins, 23 digital GPIO pins (4 of which can be analog in and 16 x PWM out). It's the same chip as the Feather RP2040 and Raspberry Pi Pico but really really small. So it's great once you've finished up a prototype, and want to make the project much smaller. It even comes with 8 MB of SPI Flash built in, for data logging, file storage, or CircuitPython/MicroPython code

* Same size and form-factor as the rest of the ItsyBitsy family and nearly-identical pinout
* Measures 1.4" x 0.7" x 0.2" (36mm x 18mm x 4mm) without headers soldered in
* RP2040 32-bit Cortex M0+ dual core running at ~125 MHz @ 3.3V logic and power
* 264 KB RAM
* 8 MB SPI FLASH chip for storing files and CircuitPython/MicroPython code storage. No EEPROM
* Tons of GPIO! 23 x GPIO pins with following capabilities:
  * Four 12 bit ADCs (one more than Pico)
  * Two I2C, Two SPI and two UART peripherals, we label one for the 'main' interface in standard ItsyBitsy locations
  * 16 x PWM outputs - for servos, LEDs, etc
  * The 10 digital 'non-ADC/non-peripheral' GPIO are consecutive for maximum PIO compatibility
* Pin #13 red LED for general purpose blinking
* RGB NeoPixel with power pin on GPIO so you can depower it for low power usages.
* Both Reset button and Bootloader select button for quick restarts (no unplugging-replugging to relaunch code)
* 3.3V regulator with 500mA peak current output
* 3.3V Power/enable pin
* Power with either USB or external output (such as a battery) - it'll automatically switch over
* Broken-out SWD pins for debug access
* 12 MHz crystal for perfect timing.
* Special Vhigh output pin gives you the higher voltage from VBAT or VUSB, for driving NeoPixels, servos, and other 5V-logic devices. Digital 5 level-shifted output for high-voltage logic level output.
* USB Micro B connector lets you access built-in ROM USB bootloader and serial port debugging

Inside the RP2040 is a 'permanent ROM' USB UF2 bootloader. What that means is when you want to program new firmware, you can hold down the BOOTSEL button while plugging it into USB (or pulling down the RUN/Reset pin to ground) and it will appear as a USB disk drive you can drag the firmware onto. Folks who have been using Adafruit products will find this very familiar - we use the technique on all our native-USB boards. Just note you don't double-click reset, instead hold down BOOTSEL during boot to enter the bootloader!

The RP2040 is a powerful chip, which has the clock speed of our M4 (SAMD51), and two cores that are equivalent to our M0 (SAMD21). Since it is an M0 chip, it does not have a floating point unit or DSP hardware support - so if you're doing something with heavy floating point math, it will be done in software and thus not as fast as an M4. For many other computational tasks, you'll get close-to-M4 speeds!

For peripherals, there are two I2C controllers, two SPI controllers, and two UARTs that are multiplexed across the GPIO - check the pinout for what pins can be set to which. There are 16 PWM channels, each pin has a channel it can be set to (ditto on the pinout).

You'll note there's no I2S peripheral, or SDIO, or camera, what's up with that? Well instead of having specific hardware support for serial-data-like peripherals like these, the RP2040 comes with the PIO state machine system which is a unique and powerful way to create custom hardware logic and data processing blocks that run on their own without taking up a CPU. For example, NeoPixels - often we bitbang the timing-specific protocol for these LEDs. For the RP2040, we instead use PIO object that reads in the data buffer and clocks out the right bitstream with perfect accuracy. Same with I2S audio in or out, LED matrix displays, 8-bit or SPI based TFTs, even VGA! In MicroPython and CircuitPython you can create PIO control commands to script the peripheral and load it in at runtime. There are 2 PIO peripherals with 4 state machines each.

At the time of launch, there is no Arduino core support for this board. There is great C/C++ support, an official MicroPython port, and a CircuitPython port! We of course recommend CircuitPython because we think it's the easiest way to get started and it has support with most of our drivers, displays, sensors, and more, supported out of the box so you can follow along with our CircuitPython projects and tutorials.

This Itsy comes with loose 0.1" headers you can solder in for breadboard use!

While the RP2040 has lots of onboard RAM (264KB), it does not have built-in FLASH memory. Instead, that is provided by the external QSPI flash chip. On this board there is 8 MB, which is shared between the program it's running and any file storage used by MicroPython or CircuitPython. When using C/C++ you get the whole flash memory, if using Python you will have about 7 MB remaining for code, files, images, fonts, etc.

### License

Adafruit invests time and resources providing this open source design, please support Adafruit and open-source hardware by purchasing products from [Adafruit](https://www.adafruit.com)!

Designed by Limor Fried/Ladyada for Adafruit Industries.

Creative Commons Attribution/Share-Alike, all text above must be included in any redistribution.
See license.txt for additional details.
