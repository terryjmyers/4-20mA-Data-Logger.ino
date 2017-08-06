# 4-20mA-Data-Logger
Schematic: https://easyeda.com/terryjmyers/New_Project-5ee76dab3cec4c7da693121a2d3a4c7d
4 Channel 4-20mA data logger using Arduino uC, RTC, SD Card.  Battery powered. Records 4 channels of 4-20mA data to a CSV file on attached SD card if any channel changes more than than the channels programmed deadband (up or down). Project was concieved and executed quickly to assist a customer with immediate data logging requirements when a purchased Omega data logger could not be commissioned.

Future improvements:

1. Add Input protection i.e. BAT85
2. Add LCd screen with rotary encoder and/or SPST momentary pushbuttons for configuration without going through the serial port
3. Move channel configuration from EEPROM to SDCard to allow user another method to configure channels
3. Change uC to ESP8266 to add wifi with socket connectivity and configuraiton webpage
4. Produce a low power version by using a 3.3V pro mini and ditching the boost converter.  Note that the program would not fit in a 3.3V pro mini for some reason, so some functionality would need to be sacrificed

Has full serial configuration interface.  Example of main menu when '?' is sent over serial:

---------------------------------------
MAIN MENU

FUNCTIONAL DESCRIPTION:
	Records 4 channels of 4-20mA data to a CSV file on attached SD card if any channel changes more than than the channels programmed deadband (up or down).
	This is not an industrial appliance, please treat accordingly:.  There is no input protection; don't touch them.  Don't drop, etc.
	Powered by (2) 2100mAh 18650 batteries. ~47mA of power for ~85h/3d8h on battery power. Low battery indicator indicates ~5% charge or ~4h remaining
	Batteries charge using any standard 5V mobile phone charger capable of at least 1.0A.  ~4h to charge to 80%, ~5h to charge to 100%. Turn off when not in use(obviously!)
	Do not remove both batteries at once or battery protection circuit will latch off and require resetting
	Unit always takes samples when powered on.  Powering the unit on is accomplished via the switch which applies battery power to the unit, or
	   when computer is plugged into the USB data port.  Battery charging can occur when the unit is switched off.
	

COMMANDS:
Note that all commands follow a CSV syntax: {letter} OR {letter},{number},...,{number}.  All commands are accessisible from all 'menus'
	1. (c)onfig - channel config and calibration
	2. (f)ile managemant and data - Prints data from storage device
	3. (t)ime,(YYYY),(MM),(DD),(HH),(MM),(SS) - Update RTC (Real time clock): e.g. t,2017,3,5,00,12,30 to set time to March 5th, 2016 @ 00:12:30

For additional information please contact Terry Myers m:XXX.XXX.XXXX

---------------------------------------
