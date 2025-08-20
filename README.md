# Conexxion Bus Displays 

![FY7000](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/FY7000.png?raw=true)

## Contact

Discord: [PixelRoute](https://discord.gg/cfKRkrfVkN)

## Findings on the AMELI FY7000 Controller and VDL LED Displays  

## 1. Introduction  
This document summarizes research and testing on the **AMELI FY7000 controller** and the **VDL LED matrix bus displays**.  
The aim is to understand their hardware, communication protocols, and potential methods for reusing them outside the original bus environment.  

---

## 2. Hardware Overview  

### 2.1 AMELI FY7000 Controller  
- **Manufacturer:** AMELI  
- **Model:** FY7000  
- **Function:** Serves as the main controller. It handles input from the driver console, GPS, and timetable system, then processes and forwards the data to the displays.  

**Connectors**  
- **Power Input:** Black = negative (–), Red = positive (+)  
- **Data Bus Input (from PC/main system):** RS232, IBIS protocol (White + Brown) *(to be confirmed)*  
- **Data Bus Output (to displays):** RS485 (White + Black) *(to be tested/confirmed)*  

**Power Requirements**  
- Voltage: 12–24 V DC  
- Current draw: ~500 mA *(to be confirmed)*  

---

### 2.2 VDL LED Displays (LDL500/150-28, LDL1650/250, LDL1280/150)  
- **Manufacturer:** VDL  
- **Models:**  
  - Rear: LDL500/150-28  
  - Front: LDL1650/250  
  - Right-side: LDL1280/150  
- **Type:** LED matrix (amber LEDs)  

**Resolution**  
- Rear LDL500/150-28: 28 × 16 pixels  
- Front LDL1650/250: *unknown (to be confirmed)*  
- Side LDL1280/150: *unknown (to be confirmed)*  

**Connectors**  
- **Power Input:** Blue = negative (–), Brown = positive (+)  
- **Data Input:** RS485 (White + Black), daisy-chain capable, connected to the FY7000 controller  

**Power Requirements**  
- Voltage: 24 V DC  
- Current draw: ~4 A per display (measured at full load)

![DISPLAY](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/387_gorinchemstation.png?raw=true)

---

## 3. Menus, Passwords, and User Inputs  

### 3.1 Maintenance Menu & Password  
When powering on, the startup screen may display **“No destination code.”**  
- Press **OK** to clear the message.  

**Steps to access the maintenance menu:**  
1. Navigate to the **wrench icon** in the bottom-left corner.  
2. Press **OK**.  

![Wrench Menu](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/IMG20250817172116.jpg?raw=true)  

3. Enter the password sequence using the keypad:  
   **DOWN → RIGHT → DOWN → RIGHT → DOWN → RIGHT → DOWN → OK**  

![Enter Password](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/IMG20250817172124.jpg?raw=true)  

If entered correctly, you will see the maintenance screen:  

![Maintenance Screen](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/IMG20250817172130.jpg?raw=true)  

Next screen after successful login:  

![Next Screen](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/IMG20250817172141.jpg?raw=true)  

---

### 3.2 Checking Protocols  
Inside the maintenance menu:  
1. Scroll down to **Factory Setup** and press **OK**.  

![Factory Setup](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/IMG20250817172147.jpg?raw=true)  

2. Select **Host** → **Protocol**.  

![Host Menu](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/IMG20250817172153.jpg?raw=true)  

3. Press **OK**. If the screen says **IBIS(3)** → the unit can accept external data.  
   If it says **None** → the unit cannot receive custom text.  

![Protocol Check](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/IMG20250817172200.jpg?raw=true)  

Confirmation of a working unit:  

![Working Unit](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/IMG20250817172208.jpg?raw=true)  

---

### 3.3 Testing Screens 

#### 3.3.1 Wiring diagram (Stock controller)

![WIRING](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/WIRING.png)
*(Under construction)*  

---

## 4. Custom Text  

### 4.1 Required Hardware (PCB)  
To send custom text, a custom PCB is required to connect the control unit to a PC.  

- Supplier: [IBIS-Wandler.de](https://ibis-wandler.de/)  
- Contact: info@ibis-wandler.de  
- Cost: ~€45  
- Requirement: Only a **data send unit** is needed (no receive unit), as no return data is transmitted.

![WANDLER](https://github.com/BlindPlayer2005/Conexxion_Bus_Displays/blob/main/images/IBIS_wandler.png)

*Note: Development of our own control units is in progress, but will take some time.*  

### 4.2 Control Software  
*(Under construction)*  

---

## 5. Custom Control Units  
*(Under construction)*  
