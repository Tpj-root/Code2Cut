



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
2. [Resistors](#2-resistors--current-limiting--voltage-division)  
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




