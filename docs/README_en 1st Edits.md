# iSpindle Documentation

***Translation is work in progress, feel free to contribute***
Update 03/12/16: Firmware 2.1.2 Wifi improvements

Update 11/29/16: Calibration and Excel Chart 

Update 28/11/16: Firmware v.2.0 - Ubidots Auto Configuration 

Update 28/11/16: Ubidots device 

Update 23:11:16: Schematic and Firmware

The iSpindelis currently in the middle of development, see the Hobbybrauer.de thread . Help is welcome and please submit your supplements by Pull Request. Many thanks to all who provide support on the basis of basic work or to find suitable hardware.

Table of Contents
	license
	principle
	Metacenter
	construction
	components
	circuit diagram
	sled
	configuration
	Ubitdots
	portal
	display
	Calibration of the spindle
	Ubidot's graphs
	CraftBeerPi
	software
________________________________________
Lisence:

Any commercial reproduction or use is in principle prohibited. Applicable patents are violated.
All rights reserverd, any commercial use is hereby prohibited and will violate applicable patents.
________________________________________

Principle
Driven by the thread alternative to stem the idea was born to recreate the commercially available electronic beer spindle.
The idea of the heeling cylinder is ingenious as easy - you do not need any external reference (except the earth) and the cylinder is extremely easy to keep clean. The inclination angle changes in relation to the buoyancy and thus directly in relation to the sugar content. No unnecessary opening to spindles and possibly contamination!
 
Therefore the idea to put an IoT device with Wifi together with an acceleration sensor and temperature sensor in a floating cylinder. There he watches all bsp. 5min, connects to my Wlan and sends its tilt angle, temperature and battery voltage to a cloud service.
Metacenter
Actually, this is the "metacentrum", the cylinder will rotate until the metacentrum in the solder is the buoyancy point. We measure this value.
It is possible to trim by adding a few grams on the ground, so that the cylinder is more upright, or on the lid, so that it will heal more.

The software calculates the Euler angle for X and Y from the XYZ acceleration values and forms the absolute angle. We compute these with the calibrated parameters for ° Plato.
________________________________________

construction
ATTENTION: This corresponds to 20.11.2016
components
⋅⋅*	Wemos D1 mini
⋅⋅*	GY-521 Gyro & Acceleration Sensor (MPU-6050 on suitable breakout board)
⋅⋅*	DS18B20 Temperature sensor
⋅⋅*	Hole grid board 3x4cm
⋅⋅*	Resistors
⋅⋅*	4k7 ohms
⋅⋅*	220k ohms
⋅⋅*	470 ohms
⋅⋅*	Microswitches
⋅⋅*	18650 LiIo Zelle(eg Panasonic NCR18650B protected or without PCB ) untested
⋅⋅*	Lipo charger module TP4056 untested
⋅⋅*	Plastic sled (template for 3D print in repo)
⋅⋅*	alternatively (breadboard) board untested )
⋅⋅*	Plastic cylinder Petling

Info
Vendor cachers-world.de unsterstützt this project by sustainably would deliver matching petling and enter the coupon code " HOBBYBRAUERgranted" (uppercase!) 20% discount. This petling-XL fits the 3D printed carriage.

Info: Currently the recomended case is only 1.44 EUR.  In 2017 it will go up to 1.52 EUR due to a 10ct increase.
Info 2: Currently sold out, re-ordered.


________________________________________

circuit diagram
see diagram
________________________________________
sled
     
 
________________________________________
configuration

Ubitdots
⋅⋅*	Initially a free account with must Ubidots.com be created
⋅⋅*	The menu API Credentials gives the Tokenby the iSpindel receives permission to write the data. 
Note this.
 
portal
By pressing the Reset Taste created the Wemos an access point with which connected you can make the necessary settings.
The iSpindel signals that it is in the configuration mode by blinking steadily every second. 
Exit the configuration mode and store the settings by pressing the menu item Start on iSpindel or wait 5 minutes. After that the iSpendil is in operating mode and transmits data.  It then goes directly into the "Deep Sleep" standby.  Ensuring that it is write-protected in normal mode.
⋅⋅*	The Ubidots Token, noted above, are now entered here.
⋅⋅*	The Intervallone must allo be intered.  This variable determines teh frequency with wich the iSpendil updates data. More frequent updates deplete the batter faster. The recomended value is 1800 seconds (= 30 minutes) to select clock.
 
⋅⋅*You get it over
  
⋅⋅*An overview of the data you can on the Infoview menu
 
After the above data has been entered and stored, the iSpindle is connected to the Wlan and Ubidots and the data is transferred. 
On the Ubidots web interface under Sources, check that the data is updated. 
Now you can see the graphs in the Dashboard.
________________________________________
display

calibration

For the conversion of angles ° in ° Plato, SG,% mas o.Ä. It is initially necessary to calibrate a reference curve. The obtained references can then be converted to a function which is stored for display. Since each self-assembled spindle will yield different measured values, one has to perform this process once.

See Calibration

Ubidot's graphs
⋅⋅*Plato formula
CraftBeerPi

Work in Progress
________________________________________
software
Firmware flashen
Firmware flashen
Used libraries
⋅⋅*https://github.com/tzapu/WiFiManager for preparing the compound (modified)
⋅⋅*Https://github.com/bblanchon/ArduinoJson

## [Calibration](Calibration_en.md)
