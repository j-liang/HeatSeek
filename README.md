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

### Correct web template usage

Building this project will require time and commitment and I believe the best way to keep track of this progress is to write it to a blog. 
In other words, to set up a website and using GitHub to host it. A web template can be retrieved from <https://github.com/six0four/StudentSenseHat>.
We cloned this repository and edited indexcontent.html or created a index.md and wrote weekly blogs of what we accomplished.

### Introduction using a system diagram

![Schematic Diagram](https://raw.githubusercontent.com/j-liang/HeatSeek/master/images/SchematicDiagram.png)

This schematic diagram will help assist in replicating HeatSeek. 
The purpose of this project is to detect and output heat temperature read from the sensor.
This sensor retrieves data by running a C program stored inside the Raspberry Pi.