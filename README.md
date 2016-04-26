# Arduino PhotoFrame
An 1.8" display with photos from SD card.

Load pictures from an SD card to a 1.8" TFT screen.
Like an electronic photo frame!

![Preview-GIF-Photoframe](https://github.com/Paul-Ver/Arduino_PhotoFrame/blob/master/Preview/gifPreview.gif)

Basic computer, programming and soldering skills required.

## Parts
- Arduino Nano (328P), will work with Arduino Uno, ATmega328/P or "better".
- 1.8" display from Adafruit, SainSmart or E-bay.
- SD card (preferably a cheap, low capacity one).
- Misc (perfboard, pin headers, wires, solder).

## How to?
- Buy the parts of Adafruit (beginners) and E-bay (advanced, seriously, you'll spend some time debugging or getting it to work).
- Connect the display to the Arduino (https://learn.adafruit.com/1-8-tft-display) or (http://www.tweaking4all.nl/hardware/arduino/sainsmart-arduino-kleuren-display/)
- Format the SD card to FAT16 (see notes)
- Put the pictures in the ROOT of the sd card, NOT in sub-folders. Try the example images first!
- Load up the firmware (of this project)
- Check the serial output (for debug-information).
- Have fun watching your pictures on a way too small display!
- Mass-produce and sell, profit!

![preview image](https://github.com/Paul-Ver/Arduino_PhotoFrame/blob/master/Preview/IMG_20160426_192340.jpg)

## Notes and errata
- images should be in the ROOT of the SD card, not in sub-folders.
- SD card has to be FAT16, NOT FAT32 or anything else. I formatted a 8GB sd-card by writing a raspbian image to it and then formatting it withouth size adjustments (https://www.raspberrypi.org/documentation/installation/installing-images/). Full 8GB didn't work in my case!
- The images need to be .BMP files with 24-bit color depth and 128x160 pixels.
- The run-time RAM usage is about maximum. Please note that creating any extra variables may lead to random behaviour/restarts (due to overflow). Try bringing down the BUFFPIXEL define and/or add more F() statements around the strings to save a few bytes of RAM.
- Currently only allows 20 photo's, since the array in which the filenames are saved is fixed to 20.
- The longer the filenames, the more RAM will be used... (software design mistake)

## Special thanks to
- Tweaking4All tutorial on the SainSmart LCD I'm using. http://www.tweaking4all.nl/
- Adafruit for the amazing libraries which push the borders of Arduino/ATmega microcontrollers.

![preview image2](https://github.com/Paul-Ver/Arduino_PhotoFrame/blob/master/Preview/IMG_20160426_192314.jpg)
