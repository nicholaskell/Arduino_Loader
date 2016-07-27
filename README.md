# Arduino Loader
This is a sample project to make it easy to start uploading code to your Arduino Leonardo with avrdude.

It mainly consists of a Makefile and a Python script that puts the Arduino Leonardo in a mode to receive code updates.


## Why is this needed?

Due to its design, the Arduino Leonardo does not have the bootloader active like earlier Arduino's. This project setup puts the Arduino in bootloader mode before attempting to upload new code.

From the [Arduino Leonardo Hardware guide](http://arduino.cc/en/Main/ArduinoBoardLeonardo):

Rather than requiring a physical press of the reset button before an upload, the Leonardo is designed in a way that allows it to be reset by software running on a connected computer. The reset is triggered when the Leonardo's virtual (CDC) serial / COM port is opened at 1200 baud and then closed. When this happens, the processor will reset, breaking the USB connection to the computer (meaning that the virtual serial / COM port will disappear). After the processor resets, the bootloader starts, remaining active for about 8 seconds. The bootloader can also be initiated by pressing the reset button on the Leonardo. Note that when the board first powers up, it will jump straight to the user sketch, if present, rather than initiating the bootloader.
	
## See also

* [Original blog post](http://nicholaskell.wordpress.com/2012/08/11/arduino-leonardo-upload-from-makefile/)
* [Arduino Leonardo guide](http://arduino.cc/en/Guide/ArduinoLeonardo)
* [Arduino Leonardo Hardware guide](http://arduino.cc/en/Main/ArduinoBoardLeonardo)

# Prerequisities

Make sure the reset.py Python script is executable:

    chmod +x reset.py

In the Makefile, make sure that the port your Arduino uses is correct:

    PORT       = /dev/ttyACM1

# Running

To run the Makefile:

	make