---
title: "meridian"
author: "axie"
description: "a modular AUV"
created_at: "2026-09-13"
---

# september 13: one small commit for me, one giant leap for PROJECTKIND!!!

oookie so i made the repo, added the base stuff: a README, the JOURNAL you're lookin at rn, kicad project files, and the BOM

note: pitching in slack as t1, i hope i get accepted!!! (my plan B's to make this a t2 and upgrade after)

this project is going to have mutiple versions adding features successively, more on this later, 

version 1 is only going to include the base AUV, SLAM, and water sampling

the base AUV's going to include 4 main PCBs

1. the main board with the SBC and breakouts to other peripherals and boards,
2. a motor controller board for movement and attachments (eg. robotic arms, water sampling),
3. a sensor controller board to process raw sensor input before feeding it into the SBC, and 
4. a battery management board to control charging and power distribution 

its hull will be made out of an acrylic tube (or tubes), O-rings, hemispheres on the front and back, and include some rails along its side for the modular attachments

the SLAM (aka. simultaneous localization & mapping), will use an array of sonar transceivers and a BLDC motor sweeping across a certain area underneath the AUV to map its surroundings
sonar array

the water sampling will use a peristaltic pump to extract water from its surroundings into a chamber for later analysis

(very) rough BOM: (for v1)
note: the stuff listed here includes the base AUV, water sampling, and recharging
hull and other enclosure bits: about 300
- SBC (lattepanda mu): 190
- mounting rods: 10*4
- breakout PCBs: 50 (not including components
- gyro: 10
- depth sensor: 80
- propeller w motor: 30
- assorted CNC / 3D printed stuff (eg propellers, attachment parts, internal frames): about 100
- battery packs: 40
- camera: 50
- water sampling stuff - stepper motor: 15, tubes and chamber: 50
- recharging stuff - solar panels: 50
wires and watertight connectors: 30

**total time spent: 2.2 hours**