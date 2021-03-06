Here are the open-source files for a Wind Speed Logger.

Based upon the DataDuino (an Arduino based SD card datalogger).


The Wind Logger was designed by Matt Little of www.re-innovation.co.uk
Contact: info@re-innovation.co.uk

Please see: www.re-innovation.co.uk and search for 'wind datalogger' for more details.

The folders in this repository include:
	
	WindLogger_PCB
	The PCB files were created in KiCAD PCB design software
	These are in Windlogger_PCB
	There are the KICAD project files and the GERBER files for both the DataDuino and the Windlogger Shield	

	WindLogger_Arduino
	Example code has been written for the Arduino IDE.
	This is for use with the Windlogger Shield.	

	WindLogger_Fixings
	The CAD design for fixing system for an anemometer and a wind vane.
	These is a work in progress.

	WindLogger_DataProcessing
	These are programs to take the data on the SD card and produce nice graphs with it.
	This is a work in progress.

	WindLogger_Instructions
	These are the instructions in a number of formats and languages.


Overview of the design:

  A PCF8563 Realt Time Clock is used to timestamp the data.
  
  Pin D3 is set up to cound pulses from a sensor (such as a anemometer or flow sensor)
  Pins D7,D8,D9 are set up to record digital information (0 or 1)
  Pins A0 to A3 are set up to record analogue information (0 to 1024)
  
  Each logger has a reference (user adjustable from 00-99).
  
  Data is written to a .csv file created on an SD card.
  A new file is created each day. If file alreay present then data is appended.
  The file name is created from the reference number and the date in the format:
  RXXDXXXX.csv, where RXX is the reference number and DXXXX is the date in the format DDMM. 
  
  Data is stored with human readable headers. Check the Arduino code for these.
  
  You can adjust the parameters of the device using serial commands. These parameters are stored in EEPROM.
  These are:
  R??E
  This will change the reference number to ??
  T??????E
  This will change the time to HHMMSS
  D??????E
  This will change the date to DDMMYY
  S?????E
  This will change the sample period to ????? seconds. Set to 00001 for 1 second data, set to 03600 for 1 hour data.
  The minimum is 1 second data. The maximum is 99999 seconds

 

Modified:
10/5/14	GitHub Repository created - Matt Little
15/8/14	Updated files with improvements made - Matt Little
 
