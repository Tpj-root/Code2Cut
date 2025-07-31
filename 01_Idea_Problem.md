



### Why do I need this machine?

 - CNC machines make it easy to build all kinds of products — parts, nuts, bolts, and other objects.
 - But the cost of these machines is too high.
 - So, I plan to start learning how to build my own CNC machine from scratch.
 - There are two major components: hardware and software.
 - The best open-source software is [LinuxCNC](https://linuxcnc.org/).
 - The hardware setup is a bit complicated, but not too difficult to manage.




In the next 20 years, a lot of hardware will end up as junk.
Some people will focus on recycling,
but I want to focus on how to reuse it — like old chips, motherboards, and displays — and use them effectively.

So, I plan to study hardware — how it works and how to use it effectively in my spare time.





Basic motherboard parts list:

1. **CPU Socket** – Holds the processor
2. **RAM Slots (DIMM)** – For memory modules
3. **Chipset (Northbridge/Southbridge or SoC)** – Controls data flow
4. **Power Connectors (24-pin, 8-pin EPS)** – Supplies power
5. **PCIe Slots** – For GPU, SSD, or expansion cards
6. **SATA Ports** – For HDDs and SSDs
7. **M.2 Slots** – For NVMe/SSD drives
8. **BIOS/UEFI Chip** – Firmware for booting
9. **VRMs (Voltage Regulator Modules)** – Power control to CPU
10. **Fan Headers** – For cooling fans
11. **I/O Ports (rear panel)** – USB, HDMI, LAN, audio, etc.
12. **CMOS Battery** – Keeps BIOS settings
13. **Onboard Audio Chip** – Controls sound output
14. **LAN Chip** – For Ethernet networking
15. **Debug LEDs / POST Code Display (some boards)** – Troubleshooting





Common **SMD (Surface Mount Device)** parts on a motherboard:

### Index
1. [Capacitors](#1-capacitors--filtering--stabilizing-voltage)  
2. [Resistors](#2-Resistors)  
3. [Inductors (Coils)](#3-inductors-coils--power-filtering)  
4. [MOSFETs](#4-mosfets--power-switching-used-in-vrms)  
5. [Diodes](#5-diodes--protection--rectification)  
6. [Crystals/Oscillators](#6-crystalsoscillators--clock-generation)  
7. [ICs (Chips)](#7-ics-chips--controllers-audio-lan-usb-bios-etc)  
8. [Transistors](#8-transistors--signal-switchingamplification)  
9. [Ferrite Beads](#9-ferrite-beads--noise-suppression)  
10. [EEPROM](#10-eeprom--stores-biosuefi)  
11. [LEDs](#11-leds--indicatorsdebug-lights)  
12. [Connectors & Pads](#12-connectors--pads--for-usb-fan-sata-etc)


1. [Capacitors](#1-capacitors--filtering--stabilizing-voltage)  

## 1. Capacitors – Filtering & stabilizing voltage

Common **capacitor types** on motherboards (SMD or through-hole):

1. **Ceramic Capacitors**

   * Small, rectangular (SMD), multilayer
   * Used for high-frequency decoupling
   * Values: pF to µF

2. **Electrolytic Capacitors**

   * Cylindrical, usually aluminum
   * Larger values (µF to mF), bulk filtering
   * Polarized (has + and -)

3. **Tantalum Capacitors**

   * Small, often yellow or black (SMD)
   * Stable, reliable, compact
   * Polarized, µF range

4. **Polymer Capacitors (Solid Capacitors)**

   * Used in VRM areas (CPU power)
   * Longer life, stable, low ESR
   * Often metallic can-style

5. **MLCC (Multilayer Ceramic Capacitor)**

   * Most common SMD type
   * Very small, high-frequency use




# Capacitor FAQ

## ❓ Why are capacitors used?

Capacitors are used to **store and release electrical energy**, and serve several key functions:

- **Filtering**: Smooth out voltage in power supplies (remove ripple).
- **Decoupling/Bypassing**: Remove noise from power lines to ICs.
- **Coupling**: Pass AC signals while blocking DC.
- **Timing**: Used with resistors to create time delays.
- **Stabilizing**: Maintain voltage levels in circuits.

---

## 📍 Where are capacitors used?

- **Power supplies**: Smoothing rectified voltage (bulk electrolytics).
- **Motherboards**: Filtering noise near CPU, RAM, chipset (MLCC, polymer).
- **Audio circuits**: Coupling signals between stages.
- **Timers (e.g., 555 IC)**: Setting delay or pulse width.
- **Switching circuits**: Snubbers to protect switches and relays.

---

## ⏰ When is a capacitor a must?

- If there's **noise or ripple** in power lines (decoupling).
- When separating **AC signals** from DC bias (coupling).
- For **startup delays** or oscillators (RC timing).
- In high-speed digital circuits (e.g., CPU, GPU VRMs).
- To stabilize **voltage regulators** or DC-DC converters.

---

## 📏 How to choose the correct value?

### Basic rules:

| Purpose        | Typical Value Range | Notes                         |
|----------------|---------------------|-------------------------------|
| Decoupling ICs | 0.01µF – 0.1µF      | Place close to IC power pins  |
| Bulk filtering | 10µF – 1000µF       | Larger for more current load  |
| Audio coupling | 1µF – 10µF          | Depends on impedance match    |
| Timing circuits| Depends on R + C    | Use formula `T = R × C`       |

### Tips:
- Check **voltage rating**: Use at least **1.5× circuit voltage**.
- For power supply: Use **low ESR** types like polymer.
- Place **one ceramic capacitor per IC**, close to its Vcc pin.

---

## 📘 Example: Decoupling on Microcontroller

```md
- Use 0.1µF ceramic capacitor between Vcc and GND
- Place physically close to the microcontroller’s power pins




For decoupling:

    One leg of the 0.1 µF ceramic capacitor goes to Vcc (power)

    Other leg goes to GND (ground)

📌 Place it as close as possible to the power pins of the IC.

This helps filter high-frequency noise before it reaches the IC.



## 2. Resistors 

 - Resistors current limiting voltage division

common **resistor types**:

---

### 1. **Carbon Film Resistors**

* Cheap, common
* ±5% tolerance
* Used in general circuits

### 2. **Metal Film Resistors**

* Better precision (±1%)
* Lower noise
* Used in audio, measurement

### 3. **Wire-Wound Resistors**

* High power rating
* Used in power supplies, motor drives

### 4. **SMD Resistors**

* Surface-mount type
* Tiny, no leads
* Used on PCBs, motherboards

### 5. **Variable Resistors (Potentiometers)**

* Adjustable resistance
* Used for volume, brightness, tuning

### 6. **Fusible Resistors**

* Acts like fuse + resistor
* Protect circuits from overcurrent

### 7. **Thermistors**

* Resistance changes with temperature
* NTC (↓R with ↑T), PTC (↑R with ↑T)
* Used in temperature sensors

### 8. **Photoresistors (LDR)**

* Resistance changes with light
* Used in light sensors



