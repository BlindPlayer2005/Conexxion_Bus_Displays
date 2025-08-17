# Conexxion_Bus_Displays

---

# Findings on AMELI FY7000 Controller and VDL LED Displays

## 1. Introduction
This document summarizes all research and test results related to the **AMELI FY7000 controller** and the **VDL LED matrix displays**.  
The goal of this research was to understand the hardware, communication protocols, and practical possibilities for reusing these displays.

---

## 2. Hardware Overview

### 2.1 AMELI FY7000 Controller
- Manufacturer: AMELI  
- Type: FY7000  
- Function: Main controller for handling input (driver console, GPS, timetable system) and sending data to displays.  
- Connectors:  
    - Power input: *Black(-) + red(+)*  
    - Data bus input (from pc/main controls): RS232 IBIS protocol *white + brown* (to be confirmed)
    - Data bus output (to display): RS485 *white + black* (to be tested and confirmed)
- Power requirements:
    - Voltage: 12V to 24V
    - Current draw: ~500mA (to be tested and confirmed)

### 2.2 VDL LDL500/150-28(backside), LDL1650/250(frontside), LDL1280/150(rightside) Displays
- Manufacturer: VDL  
- Type: VDL LDL500/150-28, LDL1650/250, LDL1280/150    
- Display type: LED matrix  
- Resolution:
    - LDL500/150-28(backside): W28 x H16
    - LDL1650/250(frontside): (unknown for now)
    - LDL1280/150(rightside): (unknown for now)
- Connectors:  
    - Power input: *Blue + Brown, where Blue is - and brown is +* 
    - Data in: RS485 *white + black* (bus communication, daisy chain capable), this will be connected to the FY7000 controller.    
- Power requirements:  
    - Voltage: 24 V DC  
    - Current draw: ~4 A per display (measured at full operation)  

---

## 3. Menu's, passwords, and general user inputs

### 3.1 Maintenance Password + checking protocol

When starting up, press "OK" to exit the no destination code message.

![](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/IMG20250817172116.jpg?raw=true)

navigate to the wrench in the lower left corner, press "OK". 

![](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/IMG20250817172124.jpg?raw=true)

and fill in the password
The password is as following: DOWN, RIGHT, DOWN, RIGHT,DOWN, RIGHT, DOWN, OK

![](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/IMG20250817172130.jpg?raw=true)

You will be presented with the next screen if the password is filled in correctly

![](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/IMG20250817172141.jpg?raw=true)

### 3.2 check protocols

When in the maintenance screen, check the communication protocols
scroll down to factory setup

![](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/IMG20250817172147.jpg?raw=true)

Press "OK", and go to "Host"

![](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/IMG20250817172153.jpg?raw=true)

Press "OK", and go to "protocol"

![](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/IMG20250817172200.jpg?raw=true)

Press "OK", If the screen says "IBIS(3)" you have a working unit that can accept data from outside
If the screen says something like "None" you wont be able to send data to the control unit to display custom strings (text).

![](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/IMG20250817172208.jpg?raw=true)

### 3.2 testing screens

(under construction)

## 4. Custom text

### 4.1 Ordering PCB

For custom text you will need a custom PCB to be able to connect to your PC

Link: https://ibis-wandler.de/
E-mail: info@ibis-wandler.de

you will only need a data send unit, not a data receive unit, as we do not have any data that will be send back to the control unit.
This will cost you roughly 45 euro.

*we are currently busy with engineering our own control units, but this will take a while*

### 4.2 Control software

(under construction).

## 5. Custom control units

(under construction).