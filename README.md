# A faster Arduino library for LPD8806 #
This is a bit of a hack for speeding up LPD8806 LED strip without using SPI. The code was originally written by Michael Noland, "Speeding up LPD8806 show() without hardware SPI" <http://michaelnoland.com/speeding-up-lpd8806-show-without-hardware-spi/>

To use, replace `strip.show()` with `strip.showCompileTime<ClockPin, DataPin>(ClockPort, DataPort)`. ClockPin/DataPin are NOT the Arduino board pin numbers, they're the actual pin offset within the port. You can find these numbers with some Googling (eg "Arduino Leonardo pin mapping"). `ClockPort` and `DataPort` are the data registers that contain the pins; on my Flora these are both `PORTD`.

For my Flora with LEDs on data pin 6 and clock pin 12, this is how I show my LEDs: `strip.showCompileTime<6, 7>(PORTD, PORTD)`

# Arduino library for LPD8806 #
This Library was written for the LPD8806 PWM LED driver chips, strips and pixels.
But the LPD8803/LPD8809 will probably work too.

## Where to Buy? ##
Pick some up at [Adafruit Industries](http://www.adafruit.com/products/306)

## Download ##
Click the Downloads Tab in the Tabbar above. 
Or follow [this](https://github.com/adafruit/LPD8806/zipball/master) link

## Installation ##
* Uncompress the Downloaded Library
* Rename the uncompressed folder to LPD8806
* Check that the LPD8806 folder contains LPD8806.cpp and LPD8806.h
* Place the LPD8806 library folder your <arduinosketchfolder>/libraries/ folder, 
  if the libraries folder does not exist - create it first!
* If your libraries folder already contains an LPD8806 folder, replace it with this version
* Restart the IDE