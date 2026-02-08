
3D-Print-Filament-Maker

 Overview

This project describes the **mechanical and electronic design of a low-cost 3D printing filament maker**.
The machine is designed to **melt plastic granulate** and extrude it into usable filament using **induction heating**, avoiding expensive commercial solutions.

The focus lies on:

* affordability
* simplicity
* reproducibility with commonly available parts



 Key Features

* Granulate-based filament production
* Induction heating for efficient and contactless melting
* Modular mechanical design
* PWM-controlled full-bridge oscillator
* Optional filament thickness control
* ESP32-based monitoring and control



 Mechanical Components

| Part            | Description                                       |
| --------------- | ------------------------------------------------- |
| Auger Drill Bit | 13 mm spiral drill for granulate transport        |
| ->              | Ø 16 mm, 100 cm length                            |
| Heating Tube    | Acts as melt channel                              |
| Force Sensor    | Used for pressure / thickness feedback (optional) |

**Part links:**

* Auger drill:
  https://www.feinewerkzeuge.de/Schlangenbohrer-13-mm-Gesamtlaenge-190-mm/312307
* Steel pipe:
  https://www.obi.de/p/4476206/arcansas-rundrohr-1-6-cm-x-100-cm-stahl
* Force-sensitive resistor:
  https://www.amazon.de/dp/B0BV7B64C5



## Electrical Components

 Power & Control

* **MEAN WELL IRM-02-12** – 12 V AC/DC power supply
* **RECOM RAC03-3.3SK** – 3.3 V regulator
* **ESP32** – control, monitoring, PWM generation

 Power Electronics

* **IRFP460PBF** – N-channel MOSFET
* **Full-bridge oscillator** (PWM controlled)
* **Ring inductors** (TLC/1A-101M-00, B78108S1475J000)
* **MKP capacitor** (6800 pF, 400 V)

 Protection & Sensing

* **B57164K103J** – NTC thermistor
* **BZX85C15-TAP** – Zener diode
* Various resistors and capacitors
* Heatsinks for all power MOSFETs



 Heating Concept: Induction Heating

The filament maker uses **high-frequency induction heating** to melt plastic granulate efficiently.
This method is:

* energy efficient
* mechanically simple
* electrically robust

More background information can be found here:
https://www.uihm.com/de/Induction-Heating-Technology/Base-details-of-High-Frequency-Induction-Heating.html



 Circuit Design

* The heating circuit is based on a **PWM-controlled full-bridge oscillator**
* Powered by a **12 V DC source**
* The circuit can be:

  * built manually using `Circuit_1.jrps`, or
  * assembled from locally sourced components

The ESP32 is powered via a **separate isolated IC** and connected **in parallel to the transformer** for control and sensing.

⚠️ **All MOSFETs must be actively cooled.**


 Filament Diameter Control

Two operating modes are supported:

1. **Without thickness sensor** – open-loop extrusion
2. **With thickness sensor** – closed-loop control using force or diameter feedback

The second method improves filament consistency but increases system complexity.



 Disclaimer

⚠️ **This project involves high currents, high frequencies, and elevated temperatures.**
It is intended for **experienced makers and engineers**.
Always follow proper electrical and mechanical safety practices.



