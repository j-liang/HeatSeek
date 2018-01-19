# Build Instructions on HeatSeek

## Table of Contents
1. [Correct web template usage](#correct-web-template-usage)
2. [Introduction using a system diagram](#introduction-using-a-system-diagram)
3. [Bill of Materials and Budget](#bill-of-materials-and-budget)
4. [Time Commitment](#time-commitment)
5. [Mechanical Assembly](#mechanical-assembly)
6. [Soldering](#soldering)
7. [Power Up] (#power-up)
8. [Unit Testing] (#unit-testing)
9. [Production Testing] (#production-testing)
10. [Reproducible?] (#reproducible)

### Correct web template usage <a name="correct-web-template-usage"> </a>

Building this project will require time and commitment and I believe the best way to keep track of this progress is to write it to a blog. 
In other words, to set up a website and using GitHub to host it. A web template can be retrieved from <https://github.com/six0four/StudentSenseHat>.
We cloned this repository and edited indexcontent.html or created a index.md and wrote weekly blogs of what we accomplished.

### Introduction using a system diagram <a name="introduction-using-a-system-diagram"></a>

![Schematic Diagram](https://raw.githubusercontent.com/j-liang/HeatSeek/master/images/SchematicDiagram.png)

This schematic diagram will help assist in replicating HeatSeek. 
The purpose of this project is to detect and output heat temperature read from the sensor.
This sensor retrieves data by running a C program stored inside the Raspberry Pi.

### Bill of Materials and Budget <a name="bill-of-materials-and-budget"></a>

The total budget to replicate this project will cost approximately $222.18.
However, I had a breadboard and jumper wires. 
If not, the total budget to replicate this project will cost approximately $242.16. 
The project consists of a Raspberry Pi 3, a Thermal Array Sensor, a Bi-Directional Logic Converter, and a breadboard. 
Below you will find the cost of each item and a link to where they can be purchased. 

1. Raspberry Pi 3, $112.99 CAD - <https://www.amazon.ca/CanaKit-Raspberry-Complete-Starter-Kit/dp/B01CCF6V3A/ref=sr_1_5?s=pc&ie=UTF8&qid=1516324581&sr=1-5&keywords=Raspberry+Pi+3>

2. Devantech Pixel 8 Thermal Array Sensor, $101.86 CAD - <https://www.robotshop.com/ca/en/devantech-8-pixel-thermal-array-sensor.html?gclid=EAIaIQobChMIvLLSyu3i2AIV3brACh11QQTWEAYYASABEgIrhPD_BwE>

3. Bi-Directional Logic Converter, $7.33 CAD - <https://elmwoodelectronics.ca/products/12009>

4. Breadboard, $5.99 - <https://www.amazon.ca/OSEPP-Breadboard-400-Points-Components-LS-00018/dp/B00EFZV2CG/ref=sr_1_5?ie=UTF8&qid=1516329412&sr=8-5&keywords=breadboard>

5. Jumper Wires, $13.99 - <https://www.amazon.ca/Foxnovo-Multicolored-40-pin-Female-Breadboard/dp/B00NPZO7CY/ref=sr_1_29?s=electronics&ie=UTF8&qid=1516329536&sr=1-29&keywords=jumper+wires>


### Time Commitment <a name"time-commitment"></a>

This project can be completed fairly quickly if the schematic diagram is followed. 
I would approximate 3 hours daily for 3-4 days should be required. 
Throughout this project, soldering, connecting wires, and testing the code will be needed to test if the sensor successfully reads data. 
At the end of the project the thermal array sensor will be able to sense ambient temperature and read temperature of an object. 

### Mechanical Assembly <a name="mechanical-assembly></a>

1.	Firstly, the Bi-Directional Logic Converter needs to be solder with parallel pins so it can be plugged into the breadboard.
2.	Once that is finished plug the logic converter and thermal array sensor to the breadboard.
3.	Using jumper wires connect the 5V PWR and GND to HV (Higher Levels Voltage) located in the top middle of the logic converter.
4.	Also, connect the 5V and GND from the thermal array sensor to the Raspberry Pi similar to the schematic diagram. 
5.	Correspondingly you must connect LV (Lower Levels Voltage) to 3.3V and GND to the Raspberry Pi. The purpose of this is to translate a 5V device to 3.3V in order to be used with the Raspberry Pi and avoid any damages. 
6.	SDA on the sensor is connected to HV2 and LV2 is connected to the I2C SDA on the Pi.
7.	Meanwhile SCL on the sensor is connected to HV1 and LV1 is connected to I2C SCL on the Pi. 
8.	The purpose of connecting to HV2 and HV1 is to translate these higher level pins on the sensor to a lower level pin on the Pi. This is to avoid any damages to the Pi as the GPIO pins are capped to 3.3V. 

### Soldering <a name="soldering></a>

This project requires to solder parallel pins to the Bi-Directional logic converter. 
The purpose of this is because we want a solid connection and not risk the wires loosening. 
If the pins were not solder to the logic converter then there’s a high risk of damaging your Pi if the wires became loose.

### Power Up

Insert the SD card to the SD card reader from the Raspberry Pi package and ensure the NOOBS operating system is installed. 
If not, the OS can be downloaded from the following link: <https://www.raspberrypi.org/downloads/noobs/>. 
If the OS is installed insert the SD card into the SD slot of the Raspberry Pi and plug in the power. 
The Raspberry Pi will boot up however, since this is the first boot up. 
Users are required to set up the operating system and configure their settings. 
An important step is to sign in to the Wi-Fi network so it can have internet connection. 
Go to Start> Raspberry Pi configuration > Interfaces and ensure I2C is enabled. 

### Unit Testing

To check if the project is connected and detecting the sensor, open a terminal and type "sudo i2cdetect –y 1". 
This command will display an output that will show address 68 at location 68. 68 is the address used for this specific sensor. 
In order to test this sensor a C program needs to be created and compiled. 
The C file can be downloaded from <https://www.robot-electronics.co.uk/files/rpi_tpa81.c>.
Save the C file as yourfilename.c and compile in the terminal using the command “gcc yourfilename.c –o yourfilename”. 
To run the program type “./yourfilename” and the program will execute. 

### Production Testing

Once the program has successfully ran the output will display the ambient temperature which is the temperature surrounding the environment. 
Additionally, it will also display 8 different temperatures which are the field of views read from 8 pixels in the sensor. 

### Reproducible?

I believe if you follow my build instructions and schematic diagram you will be able to reproduce HeatSeek. 
I have provided a GitHub, budget, instructions, diagram, code, and instructions on how to run the code. 
Therefore, I believe this project can be reproduce. 