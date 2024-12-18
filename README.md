# Ducky0
A Voron 0.2r1 CoreXY 3D Printer Modification

![alt text](https://github.com/Ducky28/Ducky0/blob/main/images/Printer%20Front.jpeg)

## Wait! But Why?
I often find myself in this situation: *sends prototype to 3D printer, 3D printer is done an hour later, realizes I'm on version 7 of the design* 
## Design goals
* Robustness
    * Stiffen up frame where possible
    * Double shear AB motor mounts for higher belt tensions
    * Ultrawide stance feet for added stability
    * Overspecced MCU and Klipper Host to avoid stability issues
* Part cooling
    * 6 4028 Delta fans for sheet cooling
    * 2 4010 blower fans for tool head part cooling
    * Dedicated 12V supply for fans
* Electronics cooling
    * As much cooling as possible for XY and Z motors
    * put heatinks on stepper stators to improve heat transfer to the air
    * Fans for high current and fast switching components (like stepper drivers)
* Extrusion system
    * [Deconstruder tool head](https://github.com/TheRealDeathsneeze/Deconstruder/tree/main)
    * 60-80mm^3/sec volumetric flow rate
    * 0.4mm high flow nozzle
    * Decently high torque extruder
* XYZ motion
    * 100,000mm/sec^2 acceleration
    * 1000mm/sec speed (600-700mm/sec printing speed)
    * Ultra light gantry
    * 5000mm/sec^2 Z acceleration
    * 200mm/sec Z speed
* Power
    * 5V 25W USB-C supply for Raspberry Pi 
    * 12V 350W PSU for fans
    * 24V 350W PSU for main electronics
    * 48V 200W PSU for XY motors
    * Separately switch 48V supply from the rest of the supplies
* Printing Capabilities
  * Fully enclosed with standard tophat and door
  * Fully contained part cooling
  * Copper heatblock for up to 450C
  * Heated bed up to 120C
  * Max observed chamber temperature: 75C

* Must be able to print these materials
     * ABS/ASA
     * PET
     * PA6/PA12
     * PLA
     * PETG
     * PC
   
## Components and Resources
* Frame Components
  * [Voron V0 Frame Brace by Jon](https://www.printables.com/model/450049-voron-v0-frame-brace)
  * [Voron V0 Stealth Handles by Maple Leaf Makers](https://www.printables.com/model/481575-voron-v0-stealth-handles)
  * Extrusions and mounting hardware used in formbot kit
* Tool head and gantry
    * [Deconstruder tool head by Becca Kay](https://github.com/TheRealDeathsneeze/Deconstruder)
    * 4010 12krpm GDSTime fans
    * NF Crazy Copper Volcano High Flow
    * 0.4mm Bondtech Brass CHT nozzle
    * LDO-36STH20-1004AHG(8T) extruder motor
    * PT1000 thermistor
    * 120W heater cartridge
* XY Motion
  * Fysetc Voron 0 ultra light gantry
  * [Double shear AB motor mounts by Driftrotor](https://github.com/Driftrotor/Voron-V0.2r1-Double-Shear-AB-Motor-Mounts/tree/main)
  * LDO-35sth52-2004AH(s35) XY motors
  * 2 3010 fans for stepper cooling
  * 2 3010 blower fans for stepper cooling
  * 2 12032 blower fans for stepper cooling
* Electronics
  * Raspberry pi 4 for Klipper Host
  * BTT SKR 3 for primary Klipper MCU
  * LDO Nitehawk 36 for tool board MCU
  * 2 Mellow Fly TMC5160 Pro drivers for XY motors
  * 2 BTT TMC2209 stepper drivers for Z and E motors
  * 4 4010 fans for electronics cooling
  * Remixed Voron 0.2 printed bottom panel. [original model by Cthulhu](https://www.printables.com/model/467247-voron-02-printed-bottom-panel)
  * [Mellow Fly HV-TMC5160 Pro Driver case by Hundsbuah](https://www.thingiverse.com/thing:5792659)
  * Embedded glass bead thermistors inside AB motors to track motor winding temperature
  * Makerbase MKS 3MOS fan mosfets
* Misc
  * 6 Delta Electronics PFB0412EN-E fans
  * Fysetc CNC bed frame
  * [4028 Air ducts by Coconut](https://github.com/CoconutDevelopment/CocobustorZero/tree/main/STLs/Coconut%20Air%20Ducts)
  * [Superwide Stance feet by Coconut](https://github.com/CoconutDevelopment/CocobustorZero/tree/main/STLs/Superwide%20Stance)
  * BTT Pi TFT70 touchscreen
  * [BTT Pi TFT70 screen enclosure by Fizzy's Tech](https://www.printables.com/model/581227-ft-btt-pi-tft70-screen-mount/files)
  * [Voron 0 Kirigami Bed by christophmuellerorg](https://github.com/christophmuellerorg/voron_0_kirigami_bed)
  * [Rainbow on a Matchstick by Blamm](https://github.com/VoronDesign/Voron-Hardware/tree/master/Daylight/Rainbow_on_a_matchstick)
  * [Lift-Off Tophat Hinges by chirpy2605](https://github.com/chirpy2605/voron/tree/main/V0/Lift-Off_Tophat_Hinges)
  * [Remixed MF Nano carbon filter by kejar31](https://www.printables.com/model/500513-voron-v0-tiny-recirculating-carbon-filter-mfnano-r)

## Short Video
[![Video](https://img.youtube.com/vi/nS1hlO0ZEqE/maxresdefault.jpg)](https://www.youtube.com/watch?v=nS1hlO0ZEqE)

## Explainer Video
[![Video](https://img.youtube.com/vi/TwCCUQ7yJMo/maxresdefault.jpg)](https://www.youtube.com/watch?v=TwCCUQ7yJMo)

## Benchy!
[![Video](https://img.youtube.com/vi/4r7pd2CCRk0/maxresdefault.jpg)](https://www.youtube.com/watch?v=4r7pd2CCRk0)

## Authors

[@Ducky28](https://github.com/Ducky28)

## Version History

* 0.1.19
     * Added Klipper Expander board for more I/O
     * [Added Remixed MF Nano carbon filter by kejar31](https://www.printables.com/model/500513-voron-v0-tiny-recirculating-carbon-filter-mfnano-r)
     * Added 2 chamber thermistors to monitor chamber temp
     * Separated fan controls for better control over different fans
     * moved pin definitions around to more sensible hardware (no more turning fans on and off with a high power heater mosfet)

* 0.1.01
     * Added Thermistors and thermal adhesive to BOM for embedding thermistors inside motors
     * Added KAMP Smart Park and Adaptive Purge routines in PRINT_START
     * Added Orcaslicer, Prusaslicer, and Cura print profiles for KAMP conditional gcodes
     * Still work in progress, things may still not work as expected!

* 0.1
    * Initial Release
    * Still work in progress, things may not work as expected!
 
## License

This project is licensed under the GPL-V3.0 License - see the LICENSE.md file for details

## Acknowledgments

* [VoronDesign](https://github.com/VoronDesign)
  * [Voron 0.2r1](https://github.com/VoronDesign/Voron-0)
  * [Klipper Expander by Tim Abraham](https://github.com/VoronDesign/Voron-Hardware/tree/master/Klipper_Expander/Documentation)
* [Klipper3D Klipper](https://github.com/Klipper3d/klipper)
  * [Klippain Shaketune by Frix-x](https://github.com/Frix-x/klippain-shaketune)
  * [Klipper TMC Autotune by Andrew McGregor](https://github.com/andrewmcgr/klipper_tmc_autotune)
  * [Klipperscreen by Jordan Ruthe](https://github.com/KlipperScreen/KlipperScreen)
  * [KAMP by kyleisah](https://github.com/kyleisah/Klipper-Adaptive-Meshing-Purging)
* [Coconut](https://github.com/CoconutDevelopment)
  * [CocobustorZero](https://github.com/CoconutDevelopment/CocobustorZero)
* [247 printing's 247 Zero Beta2](https://github.com/247printing/247zero)
* [Stefan's (CNC Kitchen) "Fast 3D printing is bad for Strength! (and how to fix it!)" video](https://youtu.be/qBvTWFEd7rk?si=yeHNLQK2HN_pLwcw) (Inspiration)
* [Vez3D VzBoT](https://github.com/VzBoT3D/VzBoT-Vz330) (Inspiration)
* All the people that have took their precious time to look at what I made and provide feedback and resources to get the project to where it is now and all the things I have learned along the way! Thank you!









































































