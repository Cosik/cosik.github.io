---
layout: post
title: Direct extruder test part one
date: 2025-12-28 16:40 +0100
tags: [3d, printing, extruder, flow]
---

Over time I searched for a good and relatively cheap extruder. My journey with 3D printing started years ago when the Anet A6 was the queen of budget machines, with a crappy extruder. The next machine, which is still alive, is my heavily modified [HEVO](thingiverse.com/thing:2254103). With this printer, another journey with extruders began.

## Bowden Extruders

At the beginning, the world of lightweight and compact extruders didn't exist. They were very heavy and bulky, and for that reason Bowden extruders were the most popular. My first one was the [Mobius 2](https://github.com/VoronDesign/Mobius-Extruder/tree/mobius-2) by Voron Design. This design is very powerful and often tore PTFE tubes out of push fittings.

![alt](/pic/extruder_test/20190131_171144.jpg){: .small-image}
*Mobius 2*

The next natural upgrade was switching to [Mobius 3](https://github.com/VoronDesign/Mobius-Extruder/tree/mobius-3), also by Voron Design — again a powerful construction.

![alt](/pic/extruder_test/20190208_180418.jpg){: .small-image}
*Mobius 3*

My last Bowden extruder was [Rappel](https://github.com/Annex-Engineering/Rappel-Extruder) by Annex-Engineering, mounted at the top of my HEVO enclosure.

![alt](/pic/extruder_test/rappel.png){: .small-image}
*Rappel*

With those extruders, after tweaking, I was able to achieve a retraction level below 2 mm. When I compare those values with direct-drive setups on Enders, such low retraction values are not attainable.

## Direct drive Extruders

Over time, direct-drive extruders became more compact and refined, so it was natural to upgrade my HEVO with one. I tested many before deciding to create this set of articles, so not all will be included here.

## Testing procedure

### Preconditions

- Pressure advance (PA) is disabled by default
- The same filament is used throughout
- The same temperature is used for each test
- Using the [Roadrunner filament sensor](https://github.com/EiNSTeiN-/roadrunner-filament-sensor) as the measurement device

### Test setup

- JAYO PLA+ filament
- Ender3 V3 SE/KE hot end with a 0.4 mm nozzle
- Klipper firmware
- Motor ldo-36sth20-1004ahg

### Test steps

1. Mount extruder
2. [Calibrate extruder steps](https://github.com/EiNSTeiN-/roadrunner-filament-sensor?tab=readme-ov-file#calibrate-the-sensors-rotation-distance)
3. Perform the [Roadrunner flow test](https://github.com/EiNSTeiN-/roadrunner-filament-sensor?tab=readme-ov-file#max-flow-calibration)
4. Run the [Inconsistent Extrusion Test](https://mihaidesigns.com/inconsistent-extrusion/) using the same G-code each time

### Calibrate extruder steps

After changing each extruder, steps are calibrated and updated. Use the command

```console
CALIBRATE_FILAMENT_SENSOR_ROTATION_DISTANCE SENSOR=roadrunner TEMP=220 LENGTH=10 SPEED=60 COUNT=10 MIN_FITNESS=0.988
```

Even if calibration of the Roadrunner sensor is not perfect, the same measurement error will apply to all tested extruders.

### Perform flow test

The flow test was executed with the `SAVE_GRAPH` flag enabled.

```console
CALIBRATE_MAX_FLOW SENSOR=roadrunner DURATION=5 COUNT=3 TEMP=220 START=5 STOP=25 SAVE_GRAPH=1 MIN_FITNESS=0.988
```

### Firmware extruder configuration

```ini
[tmc2209 extruder]
interpolate: true
sense_resistor: 0.110
run_current: 0.52
driver_TBL: 2
driver_TOFF: 2
driver_HEND: 7
driver_HSTRT: 7

[autotune_tmc extruder]
tuning_goal: performance
motor: ldo-36sth20-1004ahg
voltage: 24
extra_hysteresis: 0
tbl: 2
toff: 2
```

## List of tested extruders (in order)

![alt](/pic/extruder_test/SAM_2346.JPG){: .small-image}
*Direct drive extruders*

- [Miró](https://www.printables.com/model/1008903-the-miro-extruder)
- [Dletgbs](https://www.printables.com/model/1309632-duality-extruder)
- [ProtoXtruderNX](https://www.printables.com/model/1020272-protoxtruder-nx)
- ProtoXtruder — mixed reinforced version [this](https://www.printables.com/model/1422009-protoxtruder-skeletonised-front-plate-for-protoxtr) and [this](https://www.printables.com/model/713421-protoxtruder-hgx-xtra-rigid-back)
- Tsunami (modded by me) https://www.printables.com/model/1429510-tsunami-exturder-09
- [ProtoXtruder 2.1](https://www.printables.com/model/1052687-protoxtruder-21)

## To be continued

Tests and results will be split into a few posts; all posts will be summarized and placed on a continuously evolving separate page.
