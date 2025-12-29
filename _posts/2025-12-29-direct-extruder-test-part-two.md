---
layout: post
title: Direct extruder test part two
date: 2025-12-29 15:26 +0100
tags: [3d, printing, extruder, flow]
---

Results of performing flow tests for extruders:

* [Miró](https://www.printables.com/model/1008903-the-miro-extruder)
* [Dletgbs](https://www.printables.com/model/1309632-duality-extruder)
* [ProtoXtruderNX](https://www.printables.com/model/1020272-protoxtruder-nx)
* ProtoXtruder — mixed reinforced version [this](https://www.printables.com/model/1422009-protoxtruder-skeletonised-front-plate-for-protoxtr) and [this](https://www.printables.com/model/713421-protoxtruder-hgx-xtra-rigid-back)
* [Tsunami (modded by me)](https://www.printables.com/model/1429510-tsunami-exturder-09)
* [ProtoXtruder 2.1](https://www.printables.com/model/1052687-protoxtruder-21)

## Table of contents
{: .no_toc}

* TOC
{:toc}

## Results

### Miró

<div class="image-row">
  <figure>
    <img src="{{ '/pic/extruder_test/miro.png' | relative_url }}" alt="Plot 1">
    <figcaption>Miró</figcaption>
  </figure>
  <figure>
    <img src="{{ '/pic/extruder_test/CALIBRATE_MAX_FLOW_measured_vs_expected_speed_20251223_091121.png' | relative_url }}" alt="Plot 2">
    <figcaption>Data plot</figcaption>
  </figure>
</div>

```console
Assuming non-linear extrusion compensation is enabled, a maximum volumetric flow up to 21.021869mm³/s is suggested which will keep E speed below 8.74mm/s (which corresponds to 10.21mm/s after compensation). If the extruder is unable to reliably sustain this speed, lowering the max volumetric flow further is recommended.
Compensation coefficients: [-1.05179799  1.78440879 -0.1697739   0.0129294 ].
Enable with: ENABLE_NONLINEAR_EXTRUSION SENSOR=roadrunner ENABLE=1 COEFFICIENTS=-1.0517980,1.7844088,-0.1697739,0.0129294
Assuming no non-linear extrusion compensation, a conservative volumetric flow of 11.999999999999998mm³/s is suggested which will keep E speed below 4.99mm/s and the deviation from requested speed within a margin of 5.0%.
```

<details markdown="1">

<summary>Full klipper console log</summary>

```console
Heater turned off
Saved CALIBRATE_MAX_FLOW_measured_vs_expected_speed_20251223_091121.png
Assuming non-linear extrusion compensation is enabled, a maximum volumetric flow up to 21.021869mm³/s is suggested which will keep E speed below 8.74mm/s (which corresponds to 10.21mm/s after compensation). If the extruder is unable to reliably sustain this speed, lowering the max volumetric flow further is recommended.
Compensation coefficients: [-1.05179799  1.78440879 -0.1697739   0.0129294 ].
Enable with: ENABLE_NONLINEAR_EXTRUSION SENSOR=roadrunner ENABLE=1 COEFFICIENTS=-1.0517980,1.7844088,-0.1697739,0.0129294
Assuming no non-linear extrusion compensation, a conservative volumetric flow of 11.999999999999998mm³/s is suggested which will keep E speed below 4.99mm/s and the deviation from requested speed within a margin of 5.0%.
Run 1/3 - requested=51.97mm (at speed=10.36mm/s, flow=24.91mm³/s), measured=42.65mm in 5.03 seconds (at speed=8.67mm/s, flow=20.86mm³/s) = 16.54% speed deviation
Run 2/3 - requested=51.97mm (at speed=10.36mm/s, flow=24.92mm³/s), measured=43.66mm in 5.03 seconds (at speed=8.76mm/s, flow=21.07mm³/s) = 15.71% speed deviation
Run 3/3 - requested=51.97mm (at speed=10.36mm/s, flow=24.92mm³/s), measured=43.38mm in 5.13 seconds (at speed=8.78mm/s, flow=21.13mm³/s) = 15.48% speed deviation
Run 1/3 - requested=49.89mm (at speed=9.96mm/s, flow=23.96mm³/s), measured=42.83mm in 4.93 seconds (at speed=8.69mm/s, flow=20.90mm³/s) = 12.90% speed deviation
Run 2/3 - requested=49.89mm (at speed=9.94mm/s, flow=23.90mm³/s), measured=42.47mm in 5.03 seconds (at speed=8.57mm/s, flow=20.61mm³/s) = 14.14% speed deviation
Run 3/3 - requested=49.89mm (at speed=9.94mm/s, flow=23.91mm³/s), measured=41.60mm in 5.03 seconds (at speed=8.48mm/s, flow=20.40mm³/s) = 14.98% speed deviation
Run 1/3 - requested=47.81mm (at speed=9.53mm/s, flow=22.92mm³/s), measured=41.78mm in 5.04 seconds (at speed=8.46mm/s, flow=20.34mm³/s) = 11.55% speed deviation
Run 2/3 - requested=47.81mm (at speed=9.53mm/s, flow=22.93mm³/s), measured=42.01mm in 5.03 seconds (at speed=8.41mm/s, flow=20.23mm³/s) = 12.04% speed deviation
Run 3/3 - requested=47.81mm (at speed=9.53mm/s, flow=22.93mm³/s), measured=41.33mm in 5.03 seconds (at speed=8.36mm/s, flow=20.11mm³/s) = 12.55% speed deviation
Run 1/3 - requested=45.73mm (at speed=9.11mm/s, flow=21.91mm³/s), measured=40.46mm in 5.03 seconds (at speed=8.19mm/s, flow=19.71mm³/s) = 10.43% speed deviation
Run 2/3 - requested=45.73mm (at speed=9.11mm/s, flow=21.92mm³/s), measured=40.59mm in 5.03 seconds (at speed=8.23mm/s, flow=19.79mm³/s) = 10.04% speed deviation
Run 3/3 - requested=45.73mm (at speed=9.12mm/s, flow=21.92mm³/s), measured=40.91mm in 5.03 seconds (at speed=8.23mm/s, flow=19.79mm³/s) = 10.03% speed deviation
Run 1/3 - requested=43.65mm (at speed=8.69mm/s, flow=20.90mm³/s), measured=38.67mm in 5.03 seconds (at speed=7.89mm/s, flow=18.98mm³/s) = 9.63% speed deviation
Run 2/3 - requested=43.65mm (at speed=8.69mm/s, flow=20.90mm³/s), measured=39.41mm in 5.03 seconds (at speed=7.91mm/s, flow=19.02mm³/s) = 9.42% speed deviation
Run 3/3 - requested=43.65mm (at speed=8.69mm/s, flow=20.91mm³/s), measured=39.13mm in 5.03 seconds (at speed=7.94mm/s, flow=19.10mm³/s) = 9.04% speed deviation
Run 1/3 - requested=41.58mm (at speed=8.29mm/s, flow=19.93mm³/s), measured=37.76mm in 5.13 seconds (at speed=7.58mm/s, flow=18.24mm³/s) = 8.82% speed deviation
Run 2/3 - requested=41.58mm (at speed=8.29mm/s, flow=19.93mm³/s), measured=37.90mm in 5.13 seconds (at speed=7.54mm/s, flow=18.14mm³/s) = 9.29% speed deviation
Run 3/3 - requested=41.58mm (at speed=8.27mm/s, flow=19.90mm³/s), measured=37.12mm in 5.03 seconds (at speed=7.51mm/s, flow=18.07mm³/s) = 9.66% speed deviation
Run 1/3 - requested=39.50mm (at speed=7.87mm/s, flow=18.92mm³/s), measured=36.07mm in 5.03 seconds (at speed=7.28mm/s, flow=17.50mm³/s) = 7.90% speed deviation
Run 2/3 - requested=39.50mm (at speed=7.87mm/s, flow=18.92mm³/s), measured=35.93mm in 5.13 seconds (at speed=7.26mm/s, flow=17.45mm³/s) = 8.15% speed deviation
Run 3/3 - requested=39.50mm (at speed=7.87mm/s, flow=18.93mm³/s), measured=35.98mm in 5.03 seconds (at speed=7.28mm/s, flow=17.52mm³/s) = 7.78% speed deviation
Run 1/3 - requested=37.42mm (at speed=7.46mm/s, flow=17.95mm³/s), measured=34.33mm in 5.03 seconds (at speed=6.94mm/s, flow=16.69mm³/s) = 7.29% speed deviation
Run 2/3 - requested=37.42mm (at speed=7.46mm/s, flow=17.95mm³/s), measured=34.06mm in 5.03 seconds (at speed=6.90mm/s, flow=16.60mm³/s) = 7.77% speed deviation
Run 3/3 - requested=37.42mm (at speed=7.46mm/s, flow=17.95mm³/s), measured=34.38mm in 5.03 seconds (at speed=6.94mm/s, flow=16.69mm³/s) = 7.27% speed deviation
Run 1/3 - requested=35.34mm (at speed=7.06mm/s, flow=16.99mm³/s), measured=32.64mm in 5.03 seconds (at speed=6.60mm/s, flow=15.89mm³/s) = 6.55% speed deviation
Run 2/3 - requested=35.34mm (at speed=7.06mm/s, flow=16.99mm³/s), measured=32.69mm in 4.93 seconds (at speed=6.62mm/s, flow=15.92mm³/s) = 6.33% speed deviation
Run 3/3 - requested=35.34mm (at speed=7.05mm/s, flow=16.95mm³/s), measured=32.69mm in 4.93 seconds (at speed=6.61mm/s, flow=15.90mm³/s) = 6.49% speed deviation
Run 1/3 - requested=33.26mm (at speed=6.64mm/s, flow=15.96mm³/s), measured=30.95mm in 5.03 seconds (at speed=6.23mm/s, flow=14.98mm³/s) = 6.40% speed deviation
Run 2/3 - requested=33.26mm (at speed=6.64mm/s, flow=15.96mm³/s), measured=31.09mm in 5.03 seconds (at speed=6.23mm/s, flow=14.98mm³/s) = 6.37% speed deviation
Run 3/3 - requested=33.26mm (at speed=6.64mm/s, flow=15.96mm³/s), measured=30.54mm in 5.13 seconds (at speed=6.20mm/s, flow=14.92mm³/s) = 6.77% speed deviation
Run 1/3 - requested=31.18mm (at speed=6.22mm/s, flow=14.96mm³/s), measured=28.85mm in 5.03 seconds (at speed=5.85mm/s, flow=14.07mm³/s) = 6.19% speed deviation
Run 2/3 - requested=31.18mm (at speed=6.22mm/s, flow=14.96mm³/s), measured=29.07mm in 5.03 seconds (at speed=5.84mm/s, flow=14.05mm³/s) = 6.33% speed deviation
Run 3/3 - requested=31.18mm (at speed=6.22mm/s, flow=14.96mm³/s), measured=28.80mm in 5.03 seconds (at speed=5.84mm/s, flow=14.06mm³/s) = 6.28% speed deviation
Run 1/3 - requested=29.10mm (at speed=5.80mm/s, flow=13.95mm³/s), measured=26.88mm in 5.04 seconds (at speed=5.51mm/s, flow=13.26mm³/s) = 5.29% speed deviation
Run 2/3 - requested=29.10mm (at speed=5.80mm/s, flow=13.95mm³/s), measured=27.25mm in 5.03 seconds (at speed=5.49mm/s, flow=13.22mm³/s) = 5.60% speed deviation
Run 3/3 - requested=29.10mm (at speed=5.80mm/s, flow=13.96mm³/s), measured=27.38mm in 5.03 seconds (at speed=5.48mm/s, flow=13.18mm³/s) = 5.84% speed deviation
Run 1/3 - requested=27.02mm (at speed=5.39mm/s, flow=12.96mm³/s), measured=25.55mm in 5.03 seconds (at speed=5.12mm/s, flow=12.32mm³/s) = 5.22% speed deviation
Run 2/3 - requested=27.02mm (at speed=5.39mm/s, flow=12.96mm³/s), measured=25.83mm in 5.03 seconds (at speed=5.14mm/s, flow=12.37mm³/s) = 4.87% speed deviation
Run 3/3 - requested=27.02mm (at speed=5.40mm/s, flow=12.98mm³/s), measured=25.37mm in 5.03 seconds (at speed=5.15mm/s, flow=12.39mm³/s) = 4.67% speed deviation
Run 1/3 - requested=24.95mm (at speed=4.97mm/s, flow=11.96mm³/s), measured=23.63mm in 5.03 seconds (at speed=4.76mm/s, flow=11.46mm³/s) = 4.50% speed deviation
Run 2/3 - requested=24.95mm (at speed=4.97mm/s, flow=11.96mm³/s), measured=23.63mm in 5.03 seconds (at speed=4.76mm/s, flow=11.45mm³/s) = 4.60% speed deviation
Run 3/3 - requested=24.95mm (at speed=4.97mm/s, flow=11.96mm³/s), measured=23.63mm in 5.03 seconds (at speed=4.76mm/s, flow=11.44mm³/s) = 4.67% speed deviation
Run 1/3 - requested=22.87mm (at speed=4.56mm/s, flow=10.96mm³/s), measured=21.62mm in 5.03 seconds (at speed=4.36mm/s, flow=10.48mm³/s) = 4.71% speed deviation
Run 2/3 - requested=22.87mm (at speed=4.56mm/s, flow=10.96mm³/s), measured=21.67mm in 5.03 seconds (at speed=4.36mm/s, flow=10.49mm³/s) = 4.68% speed deviation
Run 3/3 - requested=22.87mm (at speed=4.56mm/s, flow=10.96mm³/s), measured=21.71mm in 5.03 seconds (at speed=4.37mm/s, flow=10.52mm³/s) = 4.35% speed deviation
Run 1/3 - requested=20.79mm (at speed=4.14mm/s, flow=9.95mm³/s), measured=19.98mm in 4.93 seconds (at speed=4.04mm/s, flow=9.72mm³/s) = 2.76% speed deviation
Run 2/3 - requested=20.79mm (at speed=4.14mm/s, flow=9.96mm³/s), measured=19.93mm in 5.03 seconds (at speed=4.05mm/s, flow=9.73mm³/s) = 2.65% speed deviation
Run 3/3 - requested=20.79mm (at speed=4.14mm/s, flow=9.96mm³/s), measured=19.66mm in 5.03 seconds (at speed=3.99mm/s, flow=9.59mm³/s) = 4.14% speed deviation
Run 1/3 - requested=18.71mm (at speed=3.73mm/s, flow=8.97mm³/s), measured=17.74mm in 5.03 seconds (at speed=3.59mm/s, flow=8.63mm³/s) = 4.12% speed deviation
Run 2/3 - requested=18.71mm (at speed=3.73mm/s, flow=8.98mm³/s), measured=18.01mm in 5.03 seconds (at speed=3.58mm/s, flow=8.62mm³/s) = 4.26% speed deviation
Run 3/3 - requested=18.71mm (at speed=3.72mm/s, flow=8.96mm³/s), measured=17.60mm in 5.03 seconds (at speed=3.59mm/s, flow=8.65mm³/s) = 3.94% speed deviation
Run 1/3 - requested=16.63mm (at speed=3.31mm/s, flow=7.96mm³/s), measured=16.05mm in 5.03 seconds (at speed=3.19mm/s, flow=7.68mm³/s) = 3.99% speed deviation
Run 2/3 - requested=16.63mm (at speed=3.31mm/s, flow=7.96mm³/s), measured=15.82mm in 5.13 seconds (at speed=3.23mm/s, flow=7.78mm³/s) = 2.77% speed deviation
Run 3/3 - requested=16.63mm (at speed=3.31mm/s, flow=7.96mm³/s), measured=16.27mm in 5.03 seconds (at speed=3.25mm/s, flow=7.81mm³/s) = 2.40% speed deviation
Run 1/3 - requested=14.55mm (at speed=2.89mm/s, flow=6.96mm³/s), measured=13.85mm in 5.03 seconds (at speed=2.84mm/s, flow=6.82mm³/s) = 2.55% speed deviation
Run 2/3 - requested=14.55mm (at speed=2.89mm/s, flow=6.96mm³/s), measured=13.99mm in 5.03 seconds (at speed=2.85mm/s, flow=6.85mm³/s) = 2.20% speed deviation
Run 3/3 - requested=14.55mm (at speed=2.90mm/s, flow=6.96mm³/s), measured=14.31mm in 5.03 seconds (at speed=2.84mm/s, flow=6.83mm³/s) = 2.44% speed deviation
Run 1/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=12.11mm in 5.03 seconds (at speed=2.44mm/s, flow=5.86mm³/s) = 2.31% speed deviation
Run 2/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=12.02mm in 5.03 seconds (at speed=2.41mm/s, flow=5.80mm³/s) = 3.37% speed deviation
Run 3/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=12.11mm in 5.04 seconds (at speed=2.46mm/s, flow=5.92mm³/s) = 1.34% speed deviation
Run 1/3 - requested=10.39mm (at speed=2.06mm/s, flow=4.96mm³/s), measured=10.19mm in 5.04 seconds (at speed=2.10mm/s, flow=5.05mm³/s) = 1.02% speed deviation
Run 2/3 - requested=10.39mm (at speed=2.06mm/s, flow=4.96mm³/s), measured=10.24mm in 5.03 seconds (at speed=2.09mm/s, flow=5.03mm³/s) = 0.55% speed deviation
Run 3/3 - requested=10.39mm (at speed=2.06mm/s, flow=4.96mm³/s), measured=10.15mm in 5.04 seconds (at speed=2.03mm/s, flow=4.87mm³/s) = 2.55% speed deviation
```

</details>

---

### Dletgbs

<div class="image-row">
  <figure>
    <img src="{{ '/pic/extruder_test/dletgbs.png' | relative_url }}" alt="Plot 1">
    <figcaption>Dletgbs</figcaption>
  </figure>
  <figure>
    <img src="{{ '/pic/extruder_test/CALIBRATE_MAX_FLOW_measured_vs_expected_speed_20251223_212134.png' | relative_url }}" alt="Plot 2">
    <figcaption>Data plot</figcaption>
  </figure>
</div>

```console
Assuming non-linear extrusion compensation is enabled, a maximum volumetric flow up to 18.238827mm³/s is suggested which will keep E speed below 7.58mm/s (which corresponds to 8.58mm/s after compensation). If the extruder is unable to reliably sustain this speed, lowering the max volumetric flow further is recommended.
Compensation coefficients: [-0.42031994  1.47740002 -0.13464719  0.01271045].
Enable with: ENABLE_NONLINEAR_EXTRUSION SENSOR=roadrunner ENABLE=1 COEFFICIENTS=-0.4203199,1.4774000,-0.1346472,0.0127104
Assuming no non-linear extrusion compensation, a conservative volumetric flow of 20.0mm³/s is suggested which will keep E speed below 8.32mm/s and the deviation from requested speed within a margin of 5.0%.
```

<details markdown="1">

<summary>Full klipper console log</summary>

```console
Heater turned off
Saved CALIBRATE_MAX_FLOW_measured_vs_expected_speed_20251223_212134.png
Assuming non-linear extrusion compensation is enabled, a maximum volumetric flow up to 18.724039mm³/s is suggested which will keep E speed below 7.78mm/s (which corresponds to 8.67mm/s after compensation). If the extruder is unable to reliably sustain this speed, lowering the max volumetric flow further is recommended.
Compensation coefficients: [-0.66375761  1.63077321 -0.18471127  0.01659579].
Enable with: ENABLE_NONLINEAR_EXTRUSION SENSOR=roadrunner ENABLE=1 COEFFICIENTS=-0.6637576,1.6307732,-0.1847113,0.0165958
Assuming no non-linear extrusion compensation, a conservative volumetric flow of 20.0mm³/s is suggested which will keep E speed below 8.32mm/s and the deviation from requested speed within a margin of 5.0%.
Run 1/3 - requested=51.97mm (at speed=10.38mm/s, flow=24.97mm³/s), measured=39.31mm in 5.13 seconds (at speed=7.77mm/s, flow=18.69mm³/s) = 25.23% speed deviation
Run 2/3 - requested=51.97mm (at speed=10.36mm/s, flow=24.92mm³/s), measured=38.40mm in 5.03 seconds (at speed=7.78mm/s, flow=18.70mm³/s) = 25.19% speed deviation
Run 3/3 - requested=51.97mm (at speed=10.36mm/s, flow=24.92mm³/s), measured=39.41mm in 5.13 seconds (at speed=7.81mm/s, flow=18.78mm³/s) = 24.89% speed deviation
Run 1/3 - requested=49.89mm (at speed=9.95mm/s, flow=23.93mm³/s), measured=40.27mm in 5.03 seconds (at speed=7.80mm/s, flow=18.77mm³/s) = 21.80% speed deviation
Run 2/3 - requested=49.89mm (at speed=9.95mm/s, flow=23.93mm³/s), measured=39.68mm in 5.03 seconds (at speed=7.99mm/s, flow=19.21mm³/s) = 19.95% speed deviation
Run 3/3 - requested=49.89mm (at speed=9.96mm/s, flow=23.96mm³/s), measured=39.63mm in 5.04 seconds (at speed=7.82mm/s, flow=18.80mm³/s) = 21.67% speed deviation
Run 1/3 - requested=47.81mm (at speed=9.53mm/s, flow=22.92mm³/s), measured=39.54mm in 5.03 seconds (at speed=7.89mm/s, flow=18.97mm³/s) = 17.54% speed deviation
Run 2/3 - requested=47.81mm (at speed=9.53mm/s, flow=22.92mm³/s), measured=39.50mm in 5.03 seconds (at speed=7.83mm/s, flow=18.84mm³/s) = 18.11% speed deviation
Run 3/3 - requested=47.81mm (at speed=9.53mm/s, flow=22.93mm³/s), measured=40.14mm in 5.03 seconds (at speed=7.96mm/s, flow=19.14mm³/s) = 16.77% speed deviation
Run 1/3 - requested=45.73mm (at speed=9.12mm/s, flow=21.92mm³/s), measured=39.59mm in 5.03 seconds (at speed=7.99mm/s, flow=19.22mm³/s) = 12.63% speed deviation
Run 2/3 - requested=45.73mm (at speed=9.12mm/s, flow=21.93mm³/s), measured=39.68mm in 5.13 seconds (at speed=8.01mm/s, flow=19.27mm³/s) = 12.39% speed deviation
Run 3/3 - requested=45.73mm (at speed=9.13mm/s, flow=21.96mm³/s), measured=39.73mm in 4.93 seconds (at speed=8.12mm/s, flow=19.52mm³/s) = 11.27% speed deviation
Run 1/3 - requested=43.65mm (at speed=8.70mm/s, flow=20.93mm³/s), measured=40.69mm in 5.03 seconds (at speed=8.28mm/s, flow=19.92mm³/s) = 5.13% speed deviation
Run 2/3 - requested=43.65mm (at speed=8.71mm/s, flow=20.96mm³/s), measured=40.14mm in 5.03 seconds (at speed=8.16mm/s, flow=19.62mm³/s) = 6.56% speed deviation
Run 3/3 - requested=43.65mm (at speed=8.70mm/s, flow=20.92mm³/s), measured=40.14mm in 5.03 seconds (at speed=8.03mm/s, flow=19.32mm³/s) = 8.02% speed deviation
Run 1/3 - requested=41.58mm (at speed=8.28mm/s, flow=19.92mm³/s), measured=40.64mm in 5.03 seconds (at speed=8.23mm/s, flow=19.80mm³/s) = 1.00% speed deviation
Run 2/3 - requested=41.58mm (at speed=8.28mm/s, flow=19.92mm³/s), measured=40.00mm in 5.03 seconds (at speed=8.03mm/s, flow=19.33mm³/s) = 3.37% speed deviation
Run 3/3 - requested=41.58mm (at speed=8.29mm/s, flow=19.93mm³/s), measured=40.00mm in 5.13 seconds (at speed=8.13mm/s, flow=19.55mm³/s) = 2.27% speed deviation
Run 1/3 - requested=39.50mm (at speed=7.87mm/s, flow=18.93mm³/s), measured=38.99mm in 5.03 seconds (at speed=7.83mm/s, flow=18.83mm³/s) = 0.90% speed deviation
Run 2/3 - requested=39.50mm (at speed=7.87mm/s, flow=18.93mm³/s), measured=38.86mm in 5.13 seconds (at speed=7.83mm/s, flow=18.84mm³/s) = 0.83% speed deviation
Run 3/3 - requested=39.50mm (at speed=7.88mm/s, flow=18.95mm³/s), measured=38.81mm in 5.03 seconds (at speed=7.82mm/s, flow=18.82mm³/s) = 0.97% speed deviation
Run 1/3 - requested=37.42mm (at speed=7.48mm/s, flow=17.99mm³/s), measured=36.75mm in 5.04 seconds (at speed=7.46mm/s, flow=17.95mm³/s) = 0.29% speed deviation
Run 2/3 - requested=37.42mm (at speed=7.47mm/s, flow=17.96mm³/s), measured=36.94mm in 5.03 seconds (at speed=7.44mm/s, flow=17.90mm³/s) = 0.57% speed deviation
Run 3/3 - requested=37.42mm (at speed=7.47mm/s, flow=17.96mm³/s), measured=36.98mm in 5.03 seconds (at speed=7.42mm/s, flow=17.85mm³/s) = 0.85% speed deviation
Run 1/3 - requested=35.34mm (at speed=7.05mm/s, flow=16.96mm³/s), measured=34.79mm in 5.03 seconds (at speed=7.05mm/s, flow=16.96mm³/s) = 0.22% speed deviation
Run 2/3 - requested=35.34mm (at speed=7.05mm/s, flow=16.97mm³/s), measured=35.11mm in 5.03 seconds (at speed=7.06mm/s, flow=16.98mm³/s) = 0.12% speed deviation
Run 3/3 - requested=35.34mm (at speed=7.06mm/s, flow=16.99mm³/s), measured=34.70mm in 5.03 seconds (at speed=7.07mm/s, flow=17.00mm³/s) = 0.02% speed deviation
Run 1/3 - requested=33.26mm (at speed=6.65mm/s, flow=15.99mm³/s), measured=32.50mm in 5.03 seconds (at speed=6.62mm/s, flow=15.92mm³/s) = 0.49% speed deviation
Run 2/3 - requested=33.26mm (at speed=6.65mm/s, flow=15.99mm³/s), measured=32.87mm in 5.03 seconds (at speed=6.64mm/s, flow=15.96mm³/s) = 0.24% speed deviation
Run 3/3 - requested=33.26mm (at speed=6.64mm/s, flow=15.96mm³/s), measured=33.01mm in 5.03 seconds (at speed=6.65mm/s, flow=15.99mm³/s) = 0.06% speed deviation
Run 1/3 - requested=31.18mm (at speed=6.22mm/s, flow=14.97mm³/s), measured=30.77mm in 5.03 seconds (at speed=6.21mm/s, flow=14.94mm³/s) = 0.37% speed deviation
Run 2/3 - requested=31.18mm (at speed=6.22mm/s, flow=14.96mm³/s), measured=31.13mm in 5.04 seconds (at speed=6.24mm/s, flow=15.00mm³/s) = 0.01% speed deviation
Run 3/3 - requested=31.18mm (at speed=6.23mm/s, flow=14.99mm³/s), measured=30.54mm in 5.03 seconds (at speed=6.22mm/s, flow=14.95mm³/s) = 0.30% speed deviation
Run 1/3 - requested=29.10mm (at speed=5.82mm/s, flow=13.99mm³/s), measured=28.66mm in 5.03 seconds (at speed=5.81mm/s, flow=13.98mm³/s) = 0.12% speed deviation
Run 2/3 - requested=29.10mm (at speed=5.80mm/s, flow=13.96mm³/s), measured=28.75mm in 5.13 seconds (at speed=5.80mm/s, flow=13.94mm³/s) = 0.43% speed deviation
Run 3/3 - requested=29.10mm (at speed=5.81mm/s, flow=13.96mm³/s), measured=28.94mm in 5.03 seconds (at speed=5.81mm/s, flow=13.97mm³/s) = 0.20% speed deviation
Run 1/3 - requested=27.02mm (at speed=5.39mm/s, flow=12.97mm³/s), measured=26.88mm in 5.03 seconds (at speed=5.38mm/s, flow=12.94mm³/s) = 0.44% speed deviation
Run 2/3 - requested=27.02mm (at speed=5.40mm/s, flow=12.98mm³/s), measured=26.65mm in 5.03 seconds (at speed=5.38mm/s, flow=12.95mm³/s) = 0.42% speed deviation
Run 3/3 - requested=27.02mm (at speed=5.40mm/s, flow=12.98mm³/s), measured=26.51mm in 5.03 seconds (at speed=5.42mm/s, flow=13.03mm³/s) = 0.26% speed deviation
Run 1/3 - requested=24.95mm (at speed=4.97mm/s, flow=11.96mm³/s), measured=24.78mm in 5.03 seconds (at speed=4.98mm/s, flow=11.97mm³/s) = 0.21% speed deviation
Run 2/3 - requested=24.95mm (at speed=4.97mm/s, flow=11.96mm³/s), measured=24.64mm in 5.03 seconds (at speed=4.98mm/s, flow=11.98mm³/s) = 0.19% speed deviation
Run 3/3 - requested=24.95mm (at speed=4.97mm/s, flow=11.97mm³/s), measured=24.69mm in 5.13 seconds (at speed=4.98mm/s, flow=11.98mm³/s) = 0.15% speed deviation
Run 1/3 - requested=22.87mm (at speed=4.56mm/s, flow=10.98mm³/s), measured=22.54mm in 4.93 seconds (at speed=4.57mm/s, flow=10.99mm³/s) = 0.08% speed deviation
Run 2/3 - requested=22.87mm (at speed=4.57mm/s, flow=10.98mm³/s), measured=22.49mm in 5.03 seconds (at speed=4.55mm/s, flow=10.95mm³/s) = 0.47% speed deviation
Run 3/3 - requested=22.87mm (at speed=4.56mm/s, flow=10.96mm³/s), measured=22.54mm in 5.03 seconds (at speed=4.55mm/s, flow=10.94mm³/s) = 0.54% speed deviation
Run 1/3 - requested=20.79mm (at speed=4.14mm/s, flow=9.96mm³/s), measured=20.43mm in 5.13 seconds (at speed=4.12mm/s, flow=9.90mm³/s) = 1.02% speed deviation
Run 2/3 - requested=20.79mm (at speed=4.14mm/s, flow=9.96mm³/s), measured=20.80mm in 5.13 seconds (at speed=4.16mm/s, flow=9.99mm³/s) = 0.05% speed deviation
Run 3/3 - requested=20.79mm (at speed=4.14mm/s, flow=9.97mm³/s), measured=20.94mm in 5.13 seconds (at speed=4.17mm/s, flow=10.02mm³/s) = 0.22% speed deviation
Run 1/3 - requested=18.71mm (at speed=3.73mm/s, flow=8.98mm³/s), measured=18.29mm in 5.03 seconds (at speed=3.74mm/s, flow=9.00mm³/s) = 0.03% speed deviation
Run 2/3 - requested=18.71mm (at speed=3.72mm/s, flow=8.96mm³/s), measured=18.83mm in 5.03 seconds (at speed=3.78mm/s, flow=9.10mm³/s) = 1.15% speed deviation
Run 3/3 - requested=18.71mm (at speed=3.73mm/s, flow=8.96mm³/s), measured=18.42mm in 5.03 seconds (at speed=3.74mm/s, flow=8.98mm³/s) = 0.17% speed deviation
Run 1/3 - requested=16.63mm (at speed=3.31mm/s, flow=7.96mm³/s), measured=16.82mm in 5.03 seconds (at speed=3.35mm/s, flow=8.06mm³/s) = 0.73% speed deviation
Run 2/3 - requested=16.63mm (at speed=3.31mm/s, flow=7.96mm³/s), measured=16.23mm in 5.03 seconds (at speed=3.31mm/s, flow=7.97mm³/s) = 0.41% speed deviation
Run 3/3 - requested=16.63mm (at speed=3.31mm/s, flow=7.96mm³/s), measured=16.82mm in 5.03 seconds (at speed=3.30mm/s, flow=7.94mm³/s) = 0.75% speed deviation
Run 1/3 - requested=14.55mm (at speed=2.90mm/s, flow=6.97mm³/s), measured=14.58mm in 4.93 seconds (at speed=2.95mm/s, flow=7.11mm³/s) = 1.51% speed deviation
Run 2/3 - requested=14.55mm (at speed=2.90mm/s, flow=6.98mm³/s), measured=14.17mm in 5.03 seconds (at speed=2.92mm/s, flow=7.03mm³/s) = 0.49% speed deviation
Run 3/3 - requested=14.55mm (at speed=2.89mm/s, flow=6.96mm³/s), measured=14.35mm in 5.03 seconds (at speed=2.89mm/s, flow=6.96mm³/s) = 0.58% speed deviation
Run 1/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=12.66mm in 5.03 seconds (at speed=2.50mm/s, flow=6.02mm³/s) = 0.39% speed deviation
Run 2/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=12.85mm in 5.03 seconds (at speed=2.52mm/s, flow=6.07mm³/s) = 1.08% speed deviation
Run 3/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=12.62mm in 5.03 seconds (at speed=2.47mm/s, flow=5.94mm³/s) = 1.07% speed deviation
Run 1/3 - requested=10.39mm (at speed=2.06mm/s, flow=4.96mm³/s), measured=10.56mm in 5.03 seconds (at speed=2.09mm/s, flow=5.02mm³/s) = 0.47% speed deviation
Run 2/3 - requested=10.39mm (at speed=2.06mm/s, flow=4.96mm³/s), measured=10.42mm in 5.03 seconds (at speed=2.06mm/s, flow=4.95mm³/s) = 1.05% speed deviation
Run 3/3 - requested=10.39mm (at speed=2.06mm/s, flow=4.96mm³/s), measured=10.61mm in 5.03 seconds (at speed=2.10mm/s, flow=5.05mm³/s) = 1.01% speed deviation
```

</details>

---

### ProtoXtruderNX

<div class="image-row">
  <figure>
    <img src="{{ '/pic/extruder_test/protoxtruderNX.png' | relative_url }}" alt="Plot 1">
    <figcaption>ProtoxtruderNX</figcaption>
  </figure>
  <figure>
    <img src="{{ '/pic/extruder_test/CALIBRATE_MAX_FLOW_measured_vs_expected_speed_20251223_133523.png' | relative_url }}" alt="Plot 2">
    <figcaption>Data plot</figcaption>
  </figure>
</div>

```console
Assuming non-linear extrusion compensation is enabled, a maximum volumetric flow up to 18.724039mm³/s is suggested which will keep E speed below 7.78mm/s (which corresponds to 8.67mm/s after compensation). If the extruder is unable to reliably sustain this speed, lowering the max volumetric flow further is recommended.
Compensation coefficients: [-0.66375761  1.63077321 -0.18471127  0.01659579].
Enable with: ENABLE_NONLINEAR_EXTRUSION SENSOR=roadrunner ENABLE=1 COEFFICIENTS=-0.6637576,1.6307732,-0.1847113,0.0165958
Assuming no non-linear extrusion compensation, a conservative volumetric flow of 20.0mm³/s is suggested which will keep E speed below 8.32mm/s and the deviation from requested speed within a margin of 5.0%.
```

<details markdown="1">

<summary>Full klipper console log</summary>

```console
Saved CALIBRATE_MAX_FLOW_measured_vs_expected_speed_20251223_133523.png
Assuming non-linear extrusion compensation is enabled, a maximum volumetric flow up to 18.238827mm³/s is suggested which will keep E speed below 7.58mm/s (which corresponds to 8.58mm/s after compensation). If the extruder is unable to reliably sustain this speed, lowering the max volumetric flow further is recommended.
Compensation coefficients: [-0.42031994  1.47740002 -0.13464719  0.01271045].
Enable with: ENABLE_NONLINEAR_EXTRUSION SENSOR=roadrunner ENABLE=1 COEFFICIENTS=-0.4203199,1.4774000,-0.1346472,0.0127104
Assuming no non-linear extrusion compensation, a conservative volumetric flow of 20.0mm³/s is suggested which will keep E speed below 8.32mm/s and the deviation from requested speed within a margin of 5.0%.
Run 1/3 - requested=51.97mm (at speed=10.38mm/s, flow=24.97mm³/s), measured=37.62mm in 4.94 seconds (at speed=7.55mm/s, flow=18.16mm³/s) = 27.37% speed deviation
Run 2/3 - requested=51.97mm (at speed=10.38mm/s, flow=24.97mm³/s), measured=38.22mm in 5.03 seconds (at speed=7.46mm/s, flow=17.93mm³/s) = 28.27% speed deviation
Run 3/3 - requested=51.97mm (at speed=10.38mm/s, flow=24.97mm³/s), measured=38.35mm in 5.04 seconds (at speed=7.74mm/s, flow=18.63mm³/s) = 25.49% speed deviation
Run 1/3 - requested=49.89mm (at speed=9.95mm/s, flow=23.93mm³/s), measured=39.54mm in 4.93 seconds (at speed=7.91mm/s, flow=19.03mm³/s) = 20.71% speed deviation
Run 2/3 - requested=49.89mm (at speed=9.96mm/s, flow=23.96mm³/s), measured=39.95mm in 5.03 seconds (at speed=7.96mm/s, flow=19.15mm³/s) = 20.23% speed deviation
Run 3/3 - requested=49.89mm (at speed=9.96mm/s, flow=23.96mm³/s), measured=39.82mm in 5.14 seconds (at speed=7.88mm/s, flow=18.95mm³/s) = 21.04% speed deviation
Run 1/3 - requested=47.81mm (at speed=9.55mm/s, flow=22.97mm³/s), measured=40.05mm in 5.03 seconds (at speed=8.09mm/s, flow=19.46mm³/s) = 15.37% speed deviation
Run 2/3 - requested=47.81mm (at speed=9.53mm/s, flow=22.92mm³/s), measured=38.77mm in 5.03 seconds (at speed=8.06mm/s, flow=19.39mm³/s) = 15.68% speed deviation
Run 3/3 - requested=47.81mm (at speed=9.53mm/s, flow=22.93mm³/s), measured=39.31mm in 5.03 seconds (at speed=7.87mm/s, flow=18.94mm³/s) = 17.67% speed deviation
Run 1/3 - requested=45.73mm (at speed=9.13mm/s, flow=21.96mm³/s), measured=39.77mm in 5.04 seconds (at speed=8.10mm/s, flow=19.49mm³/s) = 11.39% speed deviation
Run 2/3 - requested=45.73mm (at speed=9.13mm/s, flow=21.96mm³/s), measured=39.45mm in 5.04 seconds (at speed=7.89mm/s, flow=18.97mm³/s) = 13.79% speed deviation
Run 3/3 - requested=45.73mm (at speed=9.13mm/s, flow=21.96mm³/s), measured=37.76mm in 5.14 seconds (at speed=7.81mm/s, flow=18.80mm³/s) = 14.56% speed deviation
Run 1/3 - requested=43.65mm (at speed=8.70mm/s, flow=20.93mm³/s), measured=40.78mm in 5.03 seconds (at speed=8.18mm/s, flow=19.68mm³/s) = 6.30% speed deviation
Run 2/3 - requested=43.65mm (at speed=8.71mm/s, flow=20.96mm³/s), measured=38.67mm in 5.03 seconds (at speed=7.92mm/s, flow=19.05mm³/s) = 9.31% speed deviation
Run 3/3 - requested=43.65mm (at speed=8.71mm/s, flow=20.96mm³/s), measured=37.67mm in 4.83 seconds (at speed=7.96mm/s, flow=19.15mm³/s) = 8.81% speed deviation
Run 1/3 - requested=41.58mm (at speed=8.28mm/s, flow=19.92mm³/s), measured=39.31mm in 5.04 seconds (at speed=7.97mm/s, flow=19.17mm³/s) = 4.13% speed deviation
Run 2/3 - requested=41.58mm (at speed=8.28mm/s, flow=19.93mm³/s), measured=39.91mm in 5.14 seconds (at speed=7.97mm/s, flow=19.18mm³/s) = 4.10% speed deviation
Run 3/3 - requested=41.58mm (at speed=8.28mm/s, flow=19.93mm³/s), measured=39.41mm in 5.03 seconds (at speed=7.95mm/s, flow=19.13mm³/s) = 4.35% speed deviation
Run 1/3 - requested=39.50mm (at speed=7.88mm/s, flow=18.96mm³/s), measured=37.39mm in 5.03 seconds (at speed=7.59mm/s, flow=18.26mm³/s) = 3.88% speed deviation
Run 2/3 - requested=39.50mm (at speed=7.87mm/s, flow=18.92mm³/s), measured=37.58mm in 5.14 seconds (at speed=7.55mm/s, flow=18.15mm³/s) = 4.47% speed deviation
Run 3/3 - requested=39.50mm (at speed=7.87mm/s, flow=18.92mm³/s), measured=37.71mm in 5.04 seconds (at speed=7.56mm/s, flow=18.19mm³/s) = 4.24% speed deviation
Run 1/3 - requested=37.42mm (at speed=7.47mm/s, flow=17.97mm³/s), measured=35.66mm in 5.14 seconds (at speed=7.19mm/s, flow=17.29mm³/s) = 3.95% speed deviation
Run 2/3 - requested=37.42mm (at speed=7.48mm/s, flow=17.99mm³/s), measured=35.25mm in 5.04 seconds (at speed=7.18mm/s, flow=17.28mm³/s) = 4.01% speed deviation
Run 3/3 - requested=37.42mm (at speed=7.48mm/s, flow=17.99mm³/s), measured=35.47mm in 5.03 seconds (at speed=7.21mm/s, flow=17.34mm³/s) = 3.65% speed deviation
Run 1/3 - requested=35.34mm (at speed=7.05mm/s, flow=16.96mm³/s), measured=33.60mm in 5.14 seconds (at speed=6.76mm/s, flow=16.26mm³/s) = 4.38% speed deviation
Run 2/3 - requested=35.34mm (at speed=7.05mm/s, flow=16.96mm³/s), measured=33.69mm in 5.03 seconds (at speed=6.75mm/s, flow=16.23mm³/s) = 4.55% speed deviation
Run 3/3 - requested=35.34mm (at speed=7.05mm/s, flow=16.96mm³/s), measured=33.60mm in 5.03 seconds (at speed=6.76mm/s, flow=16.27mm³/s) = 4.29% speed deviation
Run 1/3 - requested=33.26mm (at speed=6.65mm/s, flow=15.99mm³/s), measured=31.36mm in 4.94 seconds (at speed=6.32mm/s, flow=15.20mm³/s) = 5.01% speed deviation
Run 2/3 - requested=33.26mm (at speed=6.65mm/s, flow=15.99mm³/s), measured=31.22mm in 5.03 seconds (at speed=6.34mm/s, flow=15.25mm³/s) = 4.70% speed deviation
Run 3/3 - requested=33.26mm (at speed=6.65mm/s, flow=15.99mm³/s), measured=30.95mm in 5.03 seconds (at speed=6.30mm/s, flow=15.15mm³/s) = 5.28% speed deviation
Run 1/3 - requested=31.18mm (at speed=6.23mm/s, flow=14.99mm³/s), measured=29.39mm in 5.04 seconds (at speed=5.94mm/s, flow=14.28mm³/s) = 4.78% speed deviation
Run 2/3 - requested=31.18mm (at speed=6.23mm/s, flow=14.99mm³/s), measured=29.35mm in 5.04 seconds (at speed=5.92mm/s, flow=14.23mm³/s) = 5.12% speed deviation
Run 3/3 - requested=31.18mm (at speed=6.23mm/s, flow=14.99mm³/s), measured=29.26mm in 5.04 seconds (at speed=5.96mm/s, flow=14.34mm³/s) = 4.42% speed deviation
Run 1/3 - requested=29.10mm (at speed=5.81mm/s, flow=13.96mm³/s), measured=27.57mm in 5.13 seconds (at speed=5.48mm/s, flow=13.18mm³/s) = 5.85% speed deviation
Run 2/3 - requested=29.10mm (at speed=5.81mm/s, flow=13.98mm³/s), measured=27.06mm in 5.03 seconds (at speed=5.55mm/s, flow=13.36mm³/s) = 4.56% speed deviation
Run 3/3 - requested=29.10mm (at speed=5.81mm/s, flow=13.99mm³/s), measured=27.20mm in 5.03 seconds (at speed=5.50mm/s, flow=13.24mm³/s) = 5.46% speed deviation
Run 1/3 - requested=27.02mm (at speed=5.39mm/s, flow=12.96mm³/s), measured=25.51mm in 5.04 seconds (at speed=5.16mm/s, flow=12.41mm³/s) = 4.56% speed deviation
Run 2/3 - requested=27.02mm (at speed=5.39mm/s, flow=12.96mm³/s), measured=25.33mm in 5.13 seconds (at speed=5.11mm/s, flow=12.29mm³/s) = 5.46% speed deviation
Run 3/3 - requested=27.02mm (at speed=5.39mm/s, flow=12.96mm³/s), measured=25.69mm in 5.14 seconds (at speed=5.14mm/s, flow=12.37mm³/s) = 4.86% speed deviation
Run 1/3 - requested=24.95mm (at speed=4.98mm/s, flow=11.98mm³/s), measured=23.68mm in 5.03 seconds (at speed=4.77mm/s, flow=11.47mm³/s) = 4.43% speed deviation
Run 2/3 - requested=24.95mm (at speed=4.98mm/s, flow=11.98mm³/s), measured=23.54mm in 5.03 seconds (at speed=4.75mm/s, flow=11.44mm³/s) = 4.70% speed deviation
Run 3/3 - requested=24.95mm (at speed=4.97mm/s, flow=11.96mm³/s), measured=23.50mm in 5.13 seconds (at speed=4.71mm/s, flow=11.32mm³/s) = 5.63% speed deviation
Run 1/3 - requested=22.87mm (at speed=4.56mm/s, flow=10.97mm³/s), measured=21.94mm in 5.03 seconds (at speed=4.41mm/s, flow=10.60mm³/s) = 3.66% speed deviation
Run 2/3 - requested=22.87mm (at speed=4.56mm/s, flow=10.98mm³/s), measured=21.85mm in 5.03 seconds (at speed=4.42mm/s, flow=10.62mm³/s) = 3.44% speed deviation
Run 3/3 - requested=22.87mm (at speed=4.57mm/s, flow=10.98mm³/s), measured=21.58mm in 4.93 seconds (at speed=4.36mm/s, flow=10.50mm³/s) = 4.57% speed deviation
Run 1/3 - requested=20.79mm (at speed=4.14mm/s, flow=9.96mm³/s), measured=19.70mm in 5.04 seconds (at speed=3.98mm/s, flow=9.58mm³/s) = 4.24% speed deviation
Run 2/3 - requested=20.79mm (at speed=4.14mm/s, flow=9.96mm³/s), measured=19.70mm in 5.03 seconds (at speed=3.97mm/s, flow=9.54mm³/s) = 4.63% speed deviation
Run 3/3 - requested=20.79mm (at speed=4.14mm/s, flow=9.96mm³/s), measured=20.07mm in 5.03 seconds (at speed=4.02mm/s, flow=9.68mm³/s) = 3.25% speed deviation
Run 1/3 - requested=18.71mm (at speed=3.72mm/s, flow=8.96mm³/s), measured=18.01mm in 5.13 seconds (at speed=3.57mm/s, flow=8.58mm³/s) = 4.69% speed deviation
Run 2/3 - requested=18.71mm (at speed=3.73mm/s, flow=8.96mm³/s), measured=17.65mm in 5.03 seconds (at speed=3.60mm/s, flow=8.66mm³/s) = 3.77% speed deviation
Run 3/3 - requested=18.71mm (at speed=3.73mm/s, flow=8.96mm³/s), measured=18.29mm in 5.03 seconds (at speed=3.65mm/s, flow=8.79mm³/s) = 2.35% speed deviation
Run 1/3 - requested=16.63mm (at speed=3.31mm/s, flow=7.96mm³/s), measured=15.86mm in 5.03 seconds (at speed=3.18mm/s, flow=7.65mm³/s) = 4.36% speed deviation
Run 2/3 - requested=16.63mm (at speed=3.32mm/s, flow=7.98mm³/s), measured=16.18mm in 4.93 seconds (at speed=3.24mm/s, flow=7.80mm³/s) = 2.50% speed deviation
Run 3/3 - requested=16.63mm (at speed=3.32mm/s, flow=7.98mm³/s), measured=15.68mm in 5.13 seconds (at speed=3.22mm/s, flow=7.75mm³/s) = 3.13% speed deviation
Run 1/3 - requested=14.55mm (at speed=2.89mm/s, flow=6.96mm³/s), measured=14.08mm in 5.03 seconds (at speed=2.77mm/s, flow=6.67mm³/s) = 4.73% speed deviation
Run 2/3 - requested=14.55mm (at speed=2.89mm/s, flow=6.96mm³/s), measured=13.99mm in 5.04 seconds (at speed=2.82mm/s, flow=6.79mm³/s) = 2.95% speed deviation
Run 3/3 - requested=14.55mm (at speed=2.89mm/s, flow=6.96mm³/s), measured=13.71mm in 5.04 seconds (at speed=2.82mm/s, flow=6.78mm³/s) = 3.08% speed deviation
Run 1/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=12.16mm in 5.03 seconds (at speed=2.42mm/s, flow=5.81mm³/s) = 3.16% speed deviation
Run 2/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=11.89mm in 5.03 seconds (at speed=2.35mm/s, flow=5.65mm³/s) = 5.84% speed deviation
Run 3/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=12.07mm in 5.03 seconds (at speed=2.38mm/s, flow=5.73mm³/s) = 4.56% speed deviation
Run 1/3 - requested=10.39mm (at speed=2.07mm/s, flow=4.97mm³/s), measured=9.87mm in 4.94 seconds (at speed=1.96mm/s, flow=4.71mm³/s) = 5.84% speed deviation
Run 2/3 - requested=10.39mm (at speed=2.07mm/s, flow=4.97mm³/s), measured=9.97mm in 5.03 seconds (at speed=1.97mm/s, flow=4.74mm³/s) = 5.16% speed deviation
Run 3/3 - requested=10.39mm (at speed=2.06mm/s, flow=4.96mm³/s), measured=9.78mm in 5.03 seconds (at speed=1.95mm/s, flow=4.68mm³/s) = 6.39% speed deviation
```

</details>

---

### ProtoXtruder

<div class="image-row">
  <figure>
    <img src="{{ '/pic/extruder_test/protoxtruderNX.png' | relative_url }}" alt="Plot 1">
    <figcaption>ProtoxtruderNX</figcaption>
  </figure>
  <figure>
    <img src="{{ '/pic/extruder_test/CALIBRATE_MAX_FLOW_measured_vs_expected_speed_20251223_145610.png' | relative_url }}" alt="Plot 2">
    <figcaption>Data plot</figcaption>
  </figure>
</div>

```console
Assuming non-linear extrusion compensation is enabled, a maximum volumetric flow up to 22.058062mm³/s is suggested which will keep E speed below 9.17mm/s (which corresponds to 9.86mm/s after compensation). If the extruder is unable to reliably sustain this speed, lowering the max volumetric flow further is recommended.
Compensation coefficients: [-1.21966789  1.86072616 -0.18070818  0.0119502 ].
Enable with: ENABLE_NONLINEAR_EXTRUSION SENSOR=roadrunner ENABLE=1 COEFFICIENTS=-1.2196679,1.8607262,-0.1807082,0.0119502
Assuming no non-linear extrusion compensation, a conservative volumetric flow of 23.0mm³/s is suggested which will keep E speed below 9.56mm/s and the deviation from requested speed within a margin of 5.0%.
```

<details markdown="1">

<summary>Full klipper console log</summary>

```console
Saved CALIBRATE_MAX_FLOW_measured_vs_expected_speed_20251223_145610.png
Assuming non-linear extrusion compensation is enabled, a maximum volumetric flow up to 22.058062mm³/s is suggested which will keep E speed below 9.17mm/s (which corresponds to 9.86mm/s after compensation). If the extruder is unable to reliably sustain this speed, lowering the max volumetric flow further is recommended.
Compensation coefficients: [-1.21966789  1.86072616 -0.18070818  0.0119502 ].
Enable with: ENABLE_NONLINEAR_EXTRUSION SENSOR=roadrunner ENABLE=1 COEFFICIENTS=-1.2196679,1.8607262,-0.1807082,0.0119502
Assuming no non-linear extrusion compensation, a conservative volumetric flow of 23.0mm³/s is suggested which will keep E speed below 9.56mm/s and the deviation from requested speed within a margin of 5.0%.
Run 1/3 - requested=51.74mm (at speed=10.38mm/s, flow=24.97mm³/s), measured=45.21mm in 4.83 seconds (at speed=9.23mm/s, flow=22.21mm³/s) = 11.18% speed deviation
Run 2/3 - requested=51.97mm (at speed=10.37mm/s, flow=24.93mm³/s), measured=45.90mm in 5.13 seconds (at speed=9.15mm/s, flow=22.01mm³/s) = 11.97% speed deviation
Run 3/3 - requested=51.97mm (at speed=10.38mm/s, flow=24.96mm³/s), measured=45.58mm in 5.14 seconds (at speed=9.13mm/s, flow=21.96mm³/s) = 12.16% speed deviation
Run 1/3 - requested=49.89mm (at speed=9.95mm/s, flow=23.92mm³/s), measured=45.58mm in 5.13 seconds (at speed=9.19mm/s, flow=22.10mm³/s) = 7.90% speed deviation
Run 2/3 - requested=49.89mm (at speed=9.95mm/s, flow=23.93mm³/s), measured=45.85mm in 5.13 seconds (at speed=9.19mm/s, flow=22.10mm³/s) = 7.91% speed deviation
Run 3/3 - requested=49.89mm (at speed=9.95mm/s, flow=23.93mm³/s), measured=45.71mm in 5.13 seconds (at speed=9.21mm/s, flow=22.15mm³/s) = 7.69% speed deviation
Run 1/3 - requested=47.81mm (at speed=9.55mm/s, flow=22.97mm³/s), measured=45.12mm in 5.14 seconds (at speed=9.16mm/s, flow=22.02mm³/s) = 4.24% speed deviation
Run 2/3 - requested=47.81mm (at speed=9.53mm/s, flow=22.92mm³/s), measured=44.98mm in 5.13 seconds (at speed=9.10mm/s, flow=21.88mm³/s) = 4.87% speed deviation
Run 3/3 - requested=47.81mm (at speed=9.53mm/s, flow=22.92mm³/s), measured=44.62mm in 5.04 seconds (at speed=9.11mm/s, flow=21.90mm³/s) = 4.78% speed deviation
Run 1/3 - requested=45.73mm (at speed=9.13mm/s, flow=21.96mm³/s), measured=43.66mm in 5.03 seconds (at speed=8.89mm/s, flow=21.38mm³/s) = 2.81% speed deviation
Run 2/3 - requested=45.73mm (at speed=9.13mm/s, flow=21.96mm³/s), measured=43.89mm in 5.13 seconds (at speed=8.89mm/s, flow=21.39mm³/s) = 2.76% speed deviation
Run 3/3 - requested=45.73mm (at speed=9.13mm/s, flow=21.97mm³/s), measured=44.25mm in 5.14 seconds (at speed=8.92mm/s, flow=21.47mm³/s) = 2.42% speed deviation
Run 1/3 - requested=43.65mm (at speed=8.70mm/s, flow=20.92mm³/s), measured=42.24mm in 5.03 seconds (at speed=8.53mm/s, flow=20.51mm³/s) = 2.32% speed deviation
Run 2/3 - requested=43.65mm (at speed=8.70mm/s, flow=20.93mm³/s), measured=42.70mm in 5.14 seconds (at speed=8.55mm/s, flow=20.56mm³/s) = 2.10% speed deviation
Run 3/3 - requested=43.65mm (at speed=8.70mm/s, flow=20.93mm³/s), measured=42.24mm in 5.13 seconds (at speed=8.51mm/s, flow=20.48mm³/s) = 2.49% speed deviation
Run 1/3 - requested=41.58mm (at speed=8.28mm/s, flow=19.92mm³/s), measured=40.55mm in 5.14 seconds (at speed=8.13mm/s, flow=19.55mm³/s) = 2.24% speed deviation
Run 2/3 - requested=41.58mm (at speed=8.28mm/s, flow=19.92mm³/s), measured=40.23mm in 5.13 seconds (at speed=8.12mm/s, flow=19.53mm³/s) = 2.35% speed deviation
Run 3/3 - requested=41.58mm (at speed=8.28mm/s, flow=19.93mm³/s), measured=40.50mm in 5.13 seconds (at speed=8.13mm/s, flow=19.57mm³/s) = 2.17% speed deviation
Run 1/3 - requested=39.50mm (at speed=7.88mm/s, flow=18.96mm³/s), measured=38.45mm in 5.03 seconds (at speed=7.75mm/s, flow=18.65mm³/s) = 1.84% speed deviation
Run 2/3 - requested=39.50mm (at speed=7.87mm/s, flow=18.92mm³/s), measured=38.35mm in 5.03 seconds (at speed=7.72mm/s, flow=18.57mm³/s) = 2.27% speed deviation
Run 3/3 - requested=39.50mm (at speed=7.87mm/s, flow=18.92mm³/s), measured=38.03mm in 5.03 seconds (at speed=7.73mm/s, flow=18.58mm³/s) = 2.20% speed deviation
Run 1/3 - requested=37.42mm (at speed=7.47mm/s, flow=17.97mm³/s), measured=36.53mm in 5.03 seconds (at speed=7.35mm/s, flow=17.69mm³/s) = 1.72% speed deviation
Run 2/3 - requested=37.42mm (at speed=7.48mm/s, flow=17.99mm³/s), measured=36.25mm in 5.03 seconds (at speed=7.37mm/s, flow=17.74mm³/s) = 1.45% speed deviation
Run 3/3 - requested=37.42mm (at speed=7.48mm/s, flow=17.99mm³/s), measured=36.25mm in 5.03 seconds (at speed=7.38mm/s, flow=17.76mm³/s) = 1.32% speed deviation
Run 1/3 - requested=35.34mm (at speed=7.07mm/s, flow=17.00mm³/s), measured=34.47mm in 5.03 seconds (at speed=6.97mm/s, flow=16.76mm³/s) = 1.42% speed deviation
Run 2/3 - requested=35.34mm (at speed=7.05mm/s, flow=16.96mm³/s), measured=34.51mm in 5.03 seconds (at speed=6.96mm/s, flow=16.73mm³/s) = 1.59% speed deviation
Run 3/3 - requested=35.34mm (at speed=7.05mm/s, flow=16.96mm³/s), measured=34.47mm in 5.03 seconds (at speed=6.94mm/s, flow=16.69mm³/s) = 1.82% speed deviation
Run 1/3 - requested=33.26mm (at speed=6.65mm/s, flow=15.99mm³/s), measured=32.37mm in 5.03 seconds (at speed=6.56mm/s, flow=15.78mm³/s) = 1.39% speed deviation
Run 2/3 - requested=33.26mm (at speed=6.65mm/s, flow=15.99mm³/s), measured=32.50mm in 5.03 seconds (at speed=6.58mm/s, flow=15.83mm³/s) = 1.09% speed deviation
Run 3/3 - requested=33.26mm (at speed=6.65mm/s, flow=15.99mm³/s), measured=32.50mm in 5.03 seconds (at speed=6.56mm/s, flow=15.78mm³/s) = 1.38% speed deviation
Run 1/3 - requested=31.18mm (at speed=6.22mm/s, flow=14.97mm³/s), measured=30.40mm in 5.03 seconds (at speed=6.15mm/s, flow=14.79mm³/s) = 1.43% speed deviation
Run 2/3 - requested=31.18mm (at speed=6.23mm/s, flow=14.98mm³/s), measured=30.49mm in 5.03 seconds (at speed=6.17mm/s, flow=14.84mm³/s) = 1.08% speed deviation
Run 3/3 - requested=31.18mm (at speed=6.23mm/s, flow=14.98mm³/s), measured=30.13mm in 5.04 seconds (at speed=6.13mm/s, flow=14.75mm³/s) = 1.69% speed deviation
Run 1/3 - requested=29.10mm (at speed=5.80mm/s, flow=13.96mm³/s), measured=28.43mm in 5.03 seconds (at speed=5.74mm/s, flow=13.81mm³/s) = 1.38% speed deviation
Run 2/3 - requested=29.10mm (at speed=5.80mm/s, flow=13.96mm³/s), measured=28.53mm in 5.03 seconds (at speed=5.73mm/s, flow=13.77mm³/s) = 1.61% speed deviation
Run 3/3 - requested=29.10mm (at speed=5.81mm/s, flow=13.96mm³/s), measured=28.48mm in 5.04 seconds (at speed=5.72mm/s, flow=13.77mm³/s) = 1.67% speed deviation
Run 1/3 - requested=27.02mm (at speed=5.40mm/s, flow=12.98mm³/s), measured=26.47mm in 5.14 seconds (at speed=5.32mm/s, flow=12.80mm³/s) = 1.52% speed deviation
Run 2/3 - requested=27.02mm (at speed=5.40mm/s, flow=12.99mm³/s), measured=26.42mm in 5.03 seconds (at speed=5.34mm/s, flow=12.85mm³/s) = 1.17% speed deviation
Run 3/3 - requested=27.02mm (at speed=5.39mm/s, flow=12.96mm³/s), measured=26.24mm in 5.03 seconds (at speed=5.36mm/s, flow=12.89mm³/s) = 0.86% speed deviation
Run 1/3 - requested=24.95mm (at speed=4.98mm/s, flow=11.98mm³/s), measured=24.23mm in 5.03 seconds (at speed=4.94mm/s, flow=11.89mm³/s) = 0.92% speed deviation
Run 2/3 - requested=24.95mm (at speed=4.98mm/s, flow=11.98mm³/s), measured=24.23mm in 5.03 seconds (at speed=4.94mm/s, flow=11.88mm³/s) = 1.04% speed deviation
Run 3/3 - requested=24.95mm (at speed=4.98mm/s, flow=11.98mm³/s), measured=24.32mm in 5.14 seconds (at speed=4.92mm/s, flow=11.84mm³/s) = 1.32% speed deviation
Run 1/3 - requested=22.87mm (at speed=4.56mm/s, flow=10.96mm³/s), measured=22.54mm in 5.03 seconds (at speed=4.53mm/s, flow=10.90mm³/s) = 0.94% speed deviation
Run 2/3 - requested=22.87mm (at speed=4.56mm/s, flow=10.96mm³/s), measured=22.58mm in 5.03 seconds (at speed=4.55mm/s, flow=10.94mm³/s) = 0.54% speed deviation
Run 3/3 - requested=22.87mm (at speed=4.56mm/s, flow=10.97mm³/s), measured=22.58mm in 5.13 seconds (at speed=4.53mm/s, flow=10.90mm³/s) = 0.87% speed deviation
Run 1/3 - requested=20.79mm (at speed=4.14mm/s, flow=9.96mm³/s), measured=20.30mm in 5.03 seconds (at speed=4.09mm/s, flow=9.83mm³/s) = 1.68% speed deviation
Run 2/3 - requested=20.79mm (at speed=4.14mm/s, flow=9.96mm³/s), measured=20.11mm in 5.03 seconds (at speed=4.06mm/s, flow=9.76mm³/s) = 2.43% speed deviation
Run 3/3 - requested=20.79mm (at speed=4.14mm/s, flow=9.96mm³/s), measured=20.43mm in 5.13 seconds (at speed=4.09mm/s, flow=9.84mm³/s) = 1.57% speed deviation
Run 1/3 - requested=18.71mm (at speed=3.73mm/s, flow=8.96mm³/s), measured=18.51mm in 5.03 seconds (at speed=3.70mm/s, flow=8.89mm³/s) = 1.25% speed deviation
Run 2/3 - requested=18.71mm (at speed=3.73mm/s, flow=8.96mm³/s), measured=18.15mm in 5.03 seconds (at speed=3.69mm/s, flow=8.87mm³/s) = 1.42% speed deviation
Run 3/3 - requested=18.71mm (at speed=3.73mm/s, flow=8.96mm³/s), measured=18.70mm in 5.14 seconds (at speed=3.73mm/s, flow=8.97mm³/s) = 0.29% speed deviation
Run 1/3 - requested=16.63mm (at speed=3.32mm/s, flow=7.98mm³/s), measured=16.09mm in 5.03 seconds (at speed=3.32mm/s, flow=7.98mm³/s) = 0.28% speed deviation
Run 2/3 - requested=16.63mm (at speed=3.32mm/s, flow=7.98mm³/s), measured=16.55mm in 4.93 seconds (at speed=3.31mm/s, flow=7.96mm³/s) = 0.55% speed deviation
Run 3/3 - requested=16.63mm (at speed=3.31mm/s, flow=7.96mm³/s), measured=16.09mm in 5.03 seconds (at speed=3.27mm/s, flow=7.86mm³/s) = 1.77% speed deviation
Run 1/3 - requested=14.55mm (at speed=2.89mm/s, flow=6.96mm³/s), measured=14.26mm in 5.03 seconds (at speed=2.87mm/s, flow=6.91mm³/s) = 1.34% speed deviation
Run 2/3 - requested=14.55mm (at speed=2.90mm/s, flow=6.97mm³/s), measured=14.67mm in 5.03 seconds (at speed=2.90mm/s, flow=6.97mm³/s) = 0.45% speed deviation
Run 3/3 - requested=14.55mm (at speed=2.90mm/s, flow=6.97mm³/s), measured=14.22mm in 5.03 seconds (at speed=2.84mm/s, flow=6.84mm³/s) = 2.32% speed deviation
Run 1/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=12.16mm in 5.03 seconds (at speed=2.50mm/s, flow=6.02mm³/s) = 0.40% speed deviation
Run 2/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=12.30mm in 5.03 seconds (at speed=2.52mm/s, flow=6.07mm³/s) = 1.19% speed deviation
Run 3/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=12.21mm in 5.03 seconds (at speed=2.51mm/s, flow=6.03mm³/s) = 0.51% speed deviation
Run 1/3 - requested=10.39mm (at speed=2.06mm/s, flow=4.96mm³/s), measured=10.19mm in 5.03 seconds (at speed=2.06mm/s, flow=4.96mm³/s) = 0.84% speed deviation
Run 2/3 - requested=10.39mm (at speed=2.06mm/s, flow=4.96mm³/s), measured=10.38mm in 5.03 seconds (at speed=2.14mm/s, flow=5.14mm³/s) = 2.73% speed deviation
Run 3/3 - requested=10.39mm (at speed=2.06mm/s, flow=4.96mm³/s), measured=10.38mm in 5.03 seconds (at speed=2.12mm/s, flow=5.10mm³/s) = 2.08% speed deviation

```

</details>

---

### Tsunami (modded by me)

<div class="image-row">
  <figure>
    <img src="{{ '/pic/extruder_test/tsunami09.png' | relative_url }}" alt="Plot 1">
    <figcaption>Tsunami 0.9</figcaption>
  </figure>
  <figure>
    <img src="{{ '/pic/extruder_test/CALIBRATE_MAX_FLOW_measured_vs_expected_speed_20251223_162448.png' | relative_url }}" alt="Plot 2">
    <figcaption>Data plot</figcaption>
  </figure>
</div>

```console
Assuming non-linear extrusion compensation is enabled, a maximum volumetric flow up to 21.607349mm³/s is suggested which will keep E speed below 8.98mm/s (which corresponds to 10.18mm/s after compensation). If the extruder is unable to reliably sustain this speed, lowering the max volumetric flow further is recommended.
Compensation coefficients: [-1.38542298  2.00909215 -0.22835118  0.0164763 ].
Enable with: ENABLE_NONLINEAR_EXTRUSION SENSOR=roadrunner ENABLE=1 COEFFICIENTS=-1.3854230,2.0090922,-0.2283512,0.0164763
Assuming no non-linear extrusion compensation, a conservative volumetric flow of 19.0mm³/s is suggested which will keep E speed below 7.90mm/s and the deviation from requested speed within a margin of 5.0%.
```

<details markdown="1">

<summary>Full klipper console log</summary>

```console
Heater turned off
Saved CALIBRATE_MAX_FLOW_measured_vs_expected_speed_20251223_162448.png
Assuming non-linear extrusion compensation is enabled, a maximum volumetric flow up to 21.607349mm³/s is suggested which will keep E speed below 8.98mm/s (which corresponds to 10.18mm/s after compensation). If the extruder is unable to reliably sustain this speed, lowering the max volumetric flow further is recommended.
Compensation coefficients: [-1.38542298  2.00909215 -0.22835118  0.0164763 ].
Enable with: ENABLE_NONLINEAR_EXTRUSION SENSOR=roadrunner ENABLE=1 COEFFICIENTS=-1.3854230,2.0090922,-0.2283512,0.0164763
Assuming no non-linear extrusion compensation, a conservative volumetric flow of 19.0mm³/s is suggested which will keep E speed below 7.90mm/s and the deviation from requested speed within a margin of 5.0%.
Run 1/3 - requested=51.97mm (at speed=10.36mm/s, flow=24.92mm³/s), measured=44.02mm in 5.03 seconds (at speed=8.94mm/s, flow=21.51mm³/s) = 13.96% speed deviation
Run 2/3 - requested=51.97mm (at speed=10.36mm/s, flow=24.93mm³/s), measured=44.48mm in 5.13 seconds (at speed=8.98mm/s, flow=21.60mm³/s) = 13.58% speed deviation
Run 3/3 - requested=51.97mm (at speed=10.37mm/s, flow=24.93mm³/s), measured=44.98mm in 5.13 seconds (at speed=9.02mm/s, flow=21.71mm³/s) = 13.17% speed deviation
Run 1/3 - requested=49.89mm (at speed=9.96mm/s, flow=23.97mm³/s), measured=43.84mm in 5.03 seconds (at speed=8.93mm/s, flow=21.48mm³/s) = 10.51% speed deviation
Run 2/3 - requested=49.89mm (at speed=9.96mm/s, flow=23.97mm³/s), measured=43.89mm in 5.14 seconds (at speed=8.85mm/s, flow=21.29mm³/s) = 11.30% speed deviation
Run 3/3 - requested=49.89mm (at speed=9.94mm/s, flow=23.92mm³/s), measured=43.84mm in 5.03 seconds (at speed=8.85mm/s, flow=21.29mm³/s) = 11.28% speed deviation
Run 1/3 - requested=47.81mm (at speed=9.53mm/s, flow=22.93mm³/s), measured=43.38mm in 5.03 seconds (at speed=8.72mm/s, flow=20.98mm³/s) = 8.80% speed deviation
Run 2/3 - requested=47.81mm (at speed=9.53mm/s, flow=22.93mm³/s), measured=43.34mm in 5.03 seconds (at speed=8.73mm/s, flow=20.99mm³/s) = 8.74% speed deviation
Run 3/3 - requested=47.81mm (at speed=9.53mm/s, flow=22.93mm³/s), measured=43.15mm in 5.13 seconds (at speed=8.70mm/s, flow=20.92mm³/s) = 9.03% speed deviation
Run 1/3 - requested=45.73mm (at speed=9.13mm/s, flow=21.96mm³/s), measured=41.83mm in 4.94 seconds (at speed=8.44mm/s, flow=20.29mm³/s) = 7.77% speed deviation
Run 2/3 - requested=45.73mm (at speed=9.13mm/s, flow=21.97mm³/s), measured=41.14mm in 5.03 seconds (at speed=8.37mm/s, flow=20.12mm³/s) = 8.54% speed deviation
Run 3/3 - requested=45.73mm (at speed=9.12mm/s, flow=21.93mm³/s), measured=41.78mm in 5.03 seconds (at speed=8.42mm/s, flow=20.26mm³/s) = 7.93% speed deviation
Run 1/3 - requested=43.65mm (at speed=8.70mm/s, flow=20.93mm³/s), measured=40.55mm in 5.03 seconds (at speed=8.22mm/s, flow=19.78mm³/s) = 5.80% speed deviation
Run 2/3 - requested=43.65mm (at speed=8.70mm/s, flow=20.93mm³/s), measured=41.14mm in 5.03 seconds (at speed=8.23mm/s, flow=19.79mm³/s) = 5.77% speed deviation
Run 3/3 - requested=43.65mm (at speed=8.71mm/s, flow=20.96mm³/s), measured=40.09mm in 5.03 seconds (at speed=8.19mm/s, flow=19.69mm³/s) = 6.25% speed deviation
Run 1/3 - requested=41.58mm (at speed=8.28mm/s, flow=19.92mm³/s), measured=39.73mm in 5.03 seconds (at speed=7.98mm/s, flow=19.20mm³/s) = 4.02% speed deviation
Run 2/3 - requested=41.58mm (at speed=8.28mm/s, flow=19.92mm³/s), measured=38.90mm in 5.03 seconds (at speed=7.89mm/s, flow=18.98mm³/s) = 5.08% speed deviation
Run 3/3 - requested=41.58mm (at speed=8.28mm/s, flow=19.93mm³/s), measured=39.22mm in 5.13 seconds (at speed=7.85mm/s, flow=18.88mm³/s) = 5.61% speed deviation
Run 1/3 - requested=39.50mm (at speed=7.87mm/s, flow=18.93mm³/s), measured=37.76mm in 5.04 seconds (at speed=7.60mm/s, flow=18.29mm³/s) = 3.74% speed deviation
Run 2/3 - requested=39.50mm (at speed=7.88mm/s, flow=18.96mm³/s), measured=37.49mm in 5.03 seconds (at speed=7.66mm/s, flow=18.42mm³/s) = 3.08% speed deviation
Run 3/3 - requested=39.50mm (at speed=7.88mm/s, flow=18.96mm³/s), measured=37.67mm in 5.13 seconds (at speed=7.58mm/s, flow=18.24mm³/s) = 4.02% speed deviation
Run 1/3 - requested=37.42mm (at speed=7.47mm/s, flow=17.96mm³/s), measured=36.30mm in 5.03 seconds (at speed=7.31mm/s, flow=17.59mm³/s) = 2.27% speed deviation
Run 2/3 - requested=37.42mm (at speed=7.47mm/s, flow=17.96mm³/s), measured=36.43mm in 5.03 seconds (at speed=7.29mm/s, flow=17.54mm³/s) = 2.53% speed deviation
Run 3/3 - requested=37.42mm (at speed=7.47mm/s, flow=17.96mm³/s), measured=35.93mm in 5.03 seconds (at speed=7.23mm/s, flow=17.39mm³/s) = 3.38% speed deviation
Run 1/3 - requested=35.34mm (at speed=7.06mm/s, flow=16.99mm³/s), measured=34.19mm in 4.93 seconds (at speed=6.93mm/s, flow=16.68mm³/s) = 1.90% speed deviation
Run 2/3 - requested=35.34mm (at speed=7.06mm/s, flow=16.99mm³/s), measured=34.19mm in 5.03 seconds (at speed=6.95mm/s, flow=16.72mm³/s) = 1.66% speed deviation
Run 3/3 - requested=35.34mm (at speed=7.07mm/s, flow=16.99mm³/s), measured=34.42mm in 5.03 seconds (at speed=6.94mm/s, flow=16.70mm³/s) = 1.79% speed deviation
Run 1/3 - requested=33.26mm (at speed=6.63mm/s, flow=15.96mm³/s), measured=32.41mm in 4.93 seconds (at speed=6.54mm/s, flow=15.73mm³/s) = 1.66% speed deviation
Run 2/3 - requested=33.26mm (at speed=6.64mm/s, flow=15.96mm³/s), measured=32.41mm in 5.03 seconds (at speed=6.54mm/s, flow=15.73mm³/s) = 1.71% speed deviation
Run 3/3 - requested=33.26mm (at speed=6.64mm/s, flow=15.97mm³/s), measured=32.18mm in 5.03 seconds (at speed=6.51mm/s, flow=15.66mm³/s) = 2.13% speed deviation
Run 1/3 - requested=31.18mm (at speed=6.22mm/s, flow=14.97mm³/s), measured=30.58mm in 5.03 seconds (at speed=6.14mm/s, flow=14.76mm³/s) = 1.60% speed deviation
Run 2/3 - requested=31.18mm (at speed=6.23mm/s, flow=14.98mm³/s), measured=30.08mm in 4.94 seconds (at speed=6.15mm/s, flow=14.79mm³/s) = 1.41% speed deviation
Run 3/3 - requested=31.18mm (at speed=6.23mm/s, flow=14.99mm³/s), measured=30.45mm in 5.03 seconds (at speed=6.15mm/s, flow=14.80mm³/s) = 1.36% speed deviation
Run 1/3 - requested=29.10mm (at speed=5.82mm/s, flow=13.99mm³/s), measured=28.30mm in 5.03 seconds (at speed=5.78mm/s, flow=13.89mm³/s) = 0.78% speed deviation
Run 2/3 - requested=29.10mm (at speed=5.80mm/s, flow=13.96mm³/s), measured=28.85mm in 5.03 seconds (at speed=5.78mm/s, flow=13.89mm³/s) = 0.78% speed deviation
Run 3/3 - requested=29.10mm (at speed=5.81mm/s, flow=13.96mm³/s), measured=28.39mm in 5.03 seconds (at speed=5.76mm/s, flow=13.86mm³/s) = 1.01% speed deviation
Run 1/3 - requested=27.02mm (at speed=5.39mm/s, flow=12.97mm³/s), measured=26.47mm in 5.03 seconds (at speed=5.38mm/s, flow=12.94mm³/s) = 0.45% speed deviation
Run 2/3 - requested=27.02mm (at speed=5.40mm/s, flow=12.98mm³/s), measured=26.38mm in 4.93 seconds (at speed=5.38mm/s, flow=12.95mm³/s) = 0.40% speed deviation
Run 3/3 - requested=27.02mm (at speed=5.40mm/s, flow=12.98mm³/s), measured=26.79mm in 5.03 seconds (at speed=5.36mm/s, flow=12.89mm³/s) = 0.87% speed deviation
Run 1/3 - requested=24.95mm (at speed=4.97mm/s, flow=11.96mm³/s), measured=24.73mm in 5.03 seconds (at speed=4.94mm/s, flow=11.87mm³/s) = 1.05% speed deviation
Run 2/3 - requested=24.95mm (at speed=4.97mm/s, flow=11.96mm³/s), measured=24.64mm in 5.03 seconds (at speed=4.94mm/s, flow=11.88mm³/s) = 1.02% speed deviation
Run 3/3 - requested=24.95mm (at speed=4.97mm/s, flow=11.96mm³/s), measured=24.64mm in 5.03 seconds (at speed=4.95mm/s, flow=11.91mm³/s) = 0.73% speed deviation
Run 1/3 - requested=22.87mm (at speed=4.56mm/s, flow=10.98mm³/s), measured=22.31mm in 4.93 seconds (at speed=4.52mm/s, flow=10.86mm³/s) = 1.24% speed deviation
Run 2/3 - requested=22.87mm (at speed=4.57mm/s, flow=10.98mm³/s), measured=22.40mm in 5.03 seconds (at speed=4.53mm/s, flow=10.88mm³/s) = 1.05% speed deviation
Run 3/3 - requested=22.87mm (at speed=4.56mm/s, flow=10.96mm³/s), measured=22.40mm in 5.03 seconds (at speed=4.51mm/s, flow=10.84mm³/s) = 1.42% speed deviation
Run 1/3 - requested=20.79mm (at speed=4.14mm/s, flow=9.96mm³/s), measured=20.66mm in 5.13 seconds (at speed=4.18mm/s, flow=10.04mm³/s) = 0.43% speed deviation
Run 2/3 - requested=20.79mm (at speed=4.14mm/s, flow=9.96mm³/s), measured=20.71mm in 5.03 seconds (at speed=4.17mm/s, flow=10.02mm³/s) = 0.21% speed deviation
Run 3/3 - requested=20.79mm (at speed=4.14mm/s, flow=9.97mm³/s), measured=20.57mm in 5.03 seconds (at speed=4.13mm/s, flow=9.94mm³/s) = 0.61% speed deviation
Run 1/3 - requested=18.71mm (at speed=3.73mm/s, flow=8.96mm³/s), measured=18.61mm in 5.03 seconds (at speed=3.73mm/s, flow=8.98mm³/s) = 0.26% speed deviation
Run 2/3 - requested=18.71mm (at speed=3.73mm/s, flow=8.97mm³/s), measured=18.79mm in 5.03 seconds (at speed=3.75mm/s, flow=9.03mm³/s) = 0.30% speed deviation
Run 3/3 - requested=18.71mm (at speed=3.73mm/s, flow=8.98mm³/s), measured=18.33mm in 5.03 seconds (at speed=3.74mm/s, flow=8.99mm³/s) = 0.09% speed deviation
Run 1/3 - requested=16.63mm (at speed=3.31mm/s, flow=7.96mm³/s), measured=16.69mm in 5.03 seconds (at speed=3.32mm/s, flow=7.99mm³/s) = 0.08% speed deviation
Run 2/3 - requested=16.63mm (at speed=3.31mm/s, flow=7.96mm³/s), measured=16.64mm in 5.04 seconds (at speed=3.36mm/s, flow=8.09mm³/s) = 1.08% speed deviation
Run 3/3 - requested=16.63mm (at speed=3.31mm/s, flow=7.96mm³/s), measured=16.55mm in 5.03 seconds (at speed=3.34mm/s, flow=8.03mm³/s) = 0.43% speed deviation
Run 1/3 - requested=14.55mm (at speed=2.90mm/s, flow=6.97mm³/s), measured=14.67mm in 5.13 seconds (at speed=2.89mm/s, flow=6.95mm³/s) = 0.66% speed deviation
Run 2/3 - requested=14.55mm (at speed=2.89mm/s, flow=6.96mm³/s), measured=14.54mm in 5.13 seconds (at speed=2.93mm/s, flow=7.06mm³/s) = 0.84% speed deviation
Run 3/3 - requested=14.55mm (at speed=2.89mm/s, flow=6.96mm³/s), measured=14.22mm in 5.03 seconds (at speed=2.92mm/s, flow=7.03mm³/s) = 0.36% speed deviation
Run 1/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=12.53mm in 5.03 seconds (at speed=2.55mm/s, flow=6.14mm³/s) = 2.32% speed deviation
Run 2/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=12.53mm in 5.03 seconds (at speed=2.53mm/s, flow=6.09mm³/s) = 1.49% speed deviation
Run 3/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=12.66mm in 5.03 seconds (at speed=2.54mm/s, flow=6.11mm³/s) = 1.79% speed deviation
Run 1/3 - requested=10.39mm (at speed=2.06mm/s, flow=4.96mm³/s), measured=10.42mm in 5.03 seconds (at speed=2.08mm/s, flow=5.01mm³/s) = 0.12% speed deviation
Run 2/3 - requested=10.39mm (at speed=2.06mm/s, flow=4.96mm³/s), measured=10.47mm in 5.03 seconds (at speed=2.11mm/s, flow=5.09mm³/s) = 1.73% speed deviation
Run 3/3 - requested=10.39mm (at speed=2.06mm/s, flow=4.96mm³/s), measured=10.51mm in 5.03 seconds (at speed=2.14mm/s, flow=5.14mm³/s) = 2.83% speed deviation
```

</details>

---

### ProtoXtruder 2.1

<div class="image-row">
  <figure>
    <img src="{{ '/pic/extruder_test/protoxtruder21.png' | relative_url }}" alt="Plot 1">
    <figcaption>ProtoXtruder 2.1</figcaption>
  </figure>
  <figure>
    <img src="{{ '/pic/extruder_test/CALIBRATE_MAX_FLOW_measured_vs_expected_speed_20251223_183953.png' | relative_url }}" alt="Plot 2">
    <figcaption>Data plot</figcaption>
  </figure>
</div>

```console
Assuming non-linear extrusion compensation is enabled, a maximum volumetric flow up to 22.340251mm³/s is suggested which will keep E speed below 9.29mm/s (which corresponds to 9.77mm/s after compensation). If the extruder is unable to reliably sustain this speed, lowering the max volumetric flow further is recommended.
Compensation coefficients: [-0.68036917  1.50949007 -0.11744901  0.00819013].
Enable with: ENABLE_NONLINEAR_EXTRUSION SENSOR=roadrunner ENABLE=1 COEFFICIENTS=-0.6803692,1.5094901,-0.1174490,0.0081901
Assuming no non-linear extrusion compensation, a conservative volumetric flow of 23.0mm³/s is suggested which will keep E speed below 9.56mm/s and the deviation from requested speed within a margin of 5.0%.
```

<details markdown="1">

<summary>Full klipper console log</summary>

```console
Heater turned off
Saved CALIBRATE_MAX_FLOW_measured_vs_expected_speed_20251223_183953.png
Assuming non-linear extrusion compensation is enabled, a maximum volumetric flow up to 22.340251mm³/s is suggested which will keep E speed below 9.29mm/s (which corresponds to 9.77mm/s after compensation). If the extruder is unable to reliably sustain this speed, lowering the max volumetric flow further is recommended.
Compensation coefficients: [-0.68036917  1.50949007 -0.11744901  0.00819013].
Enable with: ENABLE_NONLINEAR_EXTRUSION SENSOR=roadrunner ENABLE=1 COEFFICIENTS=-0.6803692,1.5094901,-0.1174490,0.0081901
Assuming no non-linear extrusion compensation, a conservative volumetric flow of 23.0mm³/s is suggested which will keep E speed below 9.56mm/s and the deviation from requested speed within a margin of 5.0%.
Run 1/3 - requested=51.97mm (at speed=10.38mm/s, flow=24.97mm³/s), measured=46.54mm in 5.13 seconds (at speed=9.25mm/s, flow=22.24mm³/s) = 11.03% speed deviation
Run 2/3 - requested=51.97mm (at speed=10.36mm/s, flow=24.92mm³/s), measured=46.81mm in 5.23 seconds (at speed=9.30mm/s, flow=22.37mm³/s) = 10.52% speed deviation
Run 3/3 - requested=51.97mm (at speed=10.36mm/s, flow=24.92mm³/s), measured=46.86mm in 5.13 seconds (at speed=9.32mm/s, flow=22.41mm³/s) = 10.37% speed deviation
Run 1/3 - requested=49.89mm (at speed=9.95mm/s, flow=23.92mm³/s), measured=47.31mm in 5.24 seconds (at speed=9.40mm/s, flow=22.61mm³/s) = 5.77% speed deviation
Run 2/3 - requested=49.89mm (at speed=9.95mm/s, flow=23.93mm³/s), measured=46.17mm in 5.03 seconds (at speed=9.30mm/s, flow=22.36mm³/s) = 6.84% speed deviation
Run 3/3 - requested=49.89mm (at speed=9.96mm/s, flow=23.97mm³/s), measured=46.99mm in 5.13 seconds (at speed=9.41mm/s, flow=22.63mm³/s) = 5.69% speed deviation
Run 1/3 - requested=47.81mm (at speed=9.55mm/s, flow=22.97mm³/s), measured=46.40mm in 5.03 seconds (at speed=9.39mm/s, flow=22.58mm³/s) = 1.84% speed deviation
Run 2/3 - requested=47.81mm (at speed=9.53mm/s, flow=22.92mm³/s), measured=46.45mm in 5.13 seconds (at speed=9.37mm/s, flow=22.54mm³/s) = 2.01% speed deviation
Run 3/3 - requested=47.81mm (at speed=9.53mm/s, flow=22.92mm³/s), measured=46.54mm in 5.13 seconds (at speed=9.37mm/s, flow=22.54mm³/s) = 2.02% speed deviation
Run 1/3 - requested=45.73mm (at speed=9.12mm/s, flow=21.93mm³/s), measured=44.85mm in 5.23 seconds (at speed=9.03mm/s, flow=21.71mm³/s) = 1.31% speed deviation
Run 2/3 - requested=45.73mm (at speed=9.12mm/s, flow=21.93mm³/s), measured=44.98mm in 5.14 seconds (at speed=9.04mm/s, flow=21.74mm³/s) = 1.16% speed deviation
Run 3/3 - requested=45.73mm (at speed=9.13mm/s, flow=21.96mm³/s), measured=44.57mm in 5.03 seconds (at speed=9.04mm/s, flow=21.75mm³/s) = 1.15% speed deviation
Run 1/3 - requested=43.65mm (at speed=8.71mm/s, flow=20.96mm³/s), measured=42.42mm in 5.04 seconds (at speed=8.65mm/s, flow=20.81mm³/s) = 0.91% speed deviation
Run 2/3 - requested=43.65mm (at speed=8.70mm/s, flow=20.92mm³/s), measured=42.88mm in 5.13 seconds (at speed=8.64mm/s, flow=20.78mm³/s) = 1.03% speed deviation
Run 3/3 - requested=43.65mm (at speed=8.70mm/s, flow=20.92mm³/s), measured=43.15mm in 5.04 seconds (at speed=8.66mm/s, flow=20.83mm³/s) = 0.79% speed deviation
Run 1/3 - requested=41.58mm (at speed=8.28mm/s, flow=19.93mm³/s), measured=41.28mm in 5.03 seconds (at speed=8.28mm/s, flow=19.91mm³/s) = 0.47% speed deviation
Run 2/3 - requested=41.58mm (at speed=8.29mm/s, flow=19.93mm³/s), measured=40.91mm in 5.03 seconds (at speed=8.26mm/s, flow=19.87mm³/s) = 0.65% speed deviation
Run 3/3 - requested=41.58mm (at speed=8.29mm/s, flow=19.93mm³/s), measured=41.42mm in 5.13 seconds (at speed=8.25mm/s, flow=19.85mm³/s) = 0.73% speed deviation
Run 1/3 - requested=39.50mm (at speed=7.88mm/s, flow=18.96mm³/s), measured=38.81mm in 5.03 seconds (at speed=7.89mm/s, flow=18.98mm³/s) = 0.08% speed deviation
Run 2/3 - requested=39.50mm (at speed=7.87mm/s, flow=18.92mm³/s), measured=39.27mm in 5.03 seconds (at speed=7.86mm/s, flow=18.91mm³/s) = 0.49% speed deviation
Run 3/3 - requested=39.50mm (at speed=7.87mm/s, flow=18.93mm³/s), measured=38.90mm in 5.03 seconds (at speed=7.86mm/s, flow=18.92mm³/s) = 0.45% speed deviation
Run 1/3 - requested=37.42mm (at speed=7.47mm/s, flow=17.96mm³/s), measured=37.53mm in 5.14 seconds (at speed=7.49mm/s, flow=18.02mm³/s) = 0.10% speed deviation
Run 2/3 - requested=37.42mm (at speed=7.47mm/s, flow=17.97mm³/s), measured=37.21mm in 5.03 seconds (at speed=7.48mm/s, flow=17.98mm³/s) = 0.11% speed deviation
Run 3/3 - requested=37.42mm (at speed=7.47mm/s, flow=17.97mm³/s), measured=37.12mm in 5.04 seconds (at speed=7.50mm/s, flow=18.03mm³/s) = 0.16% speed deviation
Run 1/3 - requested=35.34mm (at speed=7.07mm/s, flow=17.00mm³/s), measured=34.93mm in 5.03 seconds (at speed=7.09mm/s, flow=17.05mm³/s) = 0.27% speed deviation
Run 2/3 - requested=35.34mm (at speed=7.07mm/s, flow=17.00mm³/s), measured=35.15mm in 5.13 seconds (at speed=7.08mm/s, flow=17.02mm³/s) = 0.13% speed deviation
Run 3/3 - requested=35.34mm (at speed=7.05mm/s, flow=16.96mm³/s), measured=35.06mm in 5.03 seconds (at speed=7.07mm/s, flow=17.01mm³/s) = 0.06% speed deviation
Run 1/3 - requested=33.26mm (at speed=6.64mm/s, flow=15.97mm³/s), measured=33.19mm in 5.03 seconds (at speed=6.66mm/s, flow=16.02mm³/s) = 0.15% speed deviation
Run 2/3 - requested=33.26mm (at speed=6.64mm/s, flow=15.96mm³/s), measured=32.87mm in 5.14 seconds (at speed=6.65mm/s, flow=15.99mm³/s) = 0.05% speed deviation
Run 3/3 - requested=33.26mm (at speed=6.65mm/s, flow=15.99mm³/s), measured=33.10mm in 5.03 seconds (at speed=6.69mm/s, flow=16.10mm³/s) = 0.62% speed deviation
Run 1/3 - requested=31.18mm (at speed=6.23mm/s, flow=14.99mm³/s), measured=30.77mm in 5.03 seconds (at speed=6.25mm/s, flow=15.03mm³/s) = 0.23% speed deviation
Run 2/3 - requested=31.18mm (at speed=6.22mm/s, flow=14.96mm³/s), measured=31.22mm in 5.03 seconds (at speed=6.27mm/s, flow=15.08mm³/s) = 0.56% speed deviation
Run 3/3 - requested=31.18mm (at speed=6.22mm/s, flow=14.96mm³/s), measured=31.27mm in 5.13 seconds (at speed=6.28mm/s, flow=15.11mm³/s) = 0.73% speed deviation
Run 1/3 - requested=29.10mm (at speed=5.81mm/s, flow=13.96mm³/s), measured=29.30mm in 5.13 seconds (at speed=5.85mm/s, flow=14.06mm³/s) = 0.45% speed deviation
Run 2/3 - requested=29.10mm (at speed=5.81mm/s, flow=13.98mm³/s), measured=28.62mm in 4.93 seconds (at speed=5.86mm/s, flow=14.10mm³/s) = 0.69% speed deviation
Run 3/3 - requested=29.10mm (at speed=5.82mm/s, flow=13.99mm³/s), measured=29.07mm in 5.04 seconds (at speed=5.85mm/s, flow=14.06mm³/s) = 0.45% speed deviation
Run 1/3 - requested=27.02mm (at speed=5.40mm/s, flow=12.99mm³/s), measured=26.79mm in 5.03 seconds (at speed=5.43mm/s, flow=13.06mm³/s) = 0.50% speed deviation
Run 2/3 - requested=27.02mm (at speed=5.39mm/s, flow=12.96mm³/s), measured=27.25mm in 5.03 seconds (at speed=5.42mm/s, flow=13.03mm³/s) = 0.25% speed deviation
Run 3/3 - requested=27.02mm (at speed=5.39mm/s, flow=12.96mm³/s), measured=26.74mm in 5.03 seconds (at speed=5.43mm/s, flow=13.07mm³/s) = 0.54% speed deviation
Run 1/3 - requested=24.95mm (at speed=4.97mm/s, flow=11.96mm³/s), measured=24.91mm in 5.04 seconds (at speed=5.02mm/s, flow=12.07mm³/s) = 0.62% speed deviation
Run 2/3 - requested=24.95mm (at speed=4.98mm/s, flow=11.98mm³/s), measured=24.64mm in 5.13 seconds (at speed=5.05mm/s, flow=12.14mm³/s) = 1.16% speed deviation
Run 3/3 - requested=24.95mm (at speed=4.98mm/s, flow=11.98mm³/s), measured=24.69mm in 5.03 seconds (at speed=5.05mm/s, flow=12.14mm³/s) = 1.18% speed deviation
Run 1/3 - requested=22.87mm (at speed=4.56mm/s, flow=10.96mm³/s), measured=22.90mm in 5.13 seconds (at speed=4.61mm/s, flow=11.10mm³/s) = 0.90% speed deviation
Run 2/3 - requested=22.87mm (at speed=4.56mm/s, flow=10.96mm³/s), measured=22.86mm in 5.03 seconds (at speed=4.61mm/s, flow=11.09mm³/s) = 0.82% speed deviation
Run 3/3 - requested=22.87mm (at speed=4.56mm/s, flow=10.97mm³/s), measured=22.86mm in 5.03 seconds (at speed=4.60mm/s, flow=11.07mm³/s) = 0.61% speed deviation
Run 1/3 - requested=20.79mm (at speed=4.15mm/s, flow=9.98mm³/s), measured=20.71mm in 4.94 seconds (at speed=4.20mm/s, flow=10.11mm³/s) = 1.10% speed deviation
Run 2/3 - requested=20.79mm (at speed=4.14mm/s, flow=9.96mm³/s), measured=20.94mm in 4.93 seconds (at speed=4.23mm/s, flow=10.17mm³/s) = 1.73% speed deviation
Run 3/3 - requested=20.79mm (at speed=4.14mm/s, flow=9.96mm³/s), measured=20.85mm in 5.03 seconds (at speed=4.22mm/s, flow=10.15mm³/s) = 1.50% speed deviation
Run 1/3 - requested=18.71mm (at speed=3.73mm/s, flow=8.96mm³/s), measured=18.56mm in 5.03 seconds (at speed=3.75mm/s, flow=9.01mm³/s) = 0.16% speed deviation
Run 2/3 - requested=18.71mm (at speed=3.73mm/s, flow=8.96mm³/s), measured=19.02mm in 5.03 seconds (at speed=3.78mm/s, flow=9.08mm³/s) = 0.90% speed deviation
Run 3/3 - requested=18.71mm (at speed=3.73mm/s, flow=8.96mm³/s), measured=18.42mm in 5.04 seconds (at speed=3.74mm/s, flow=9.00mm³/s) = 0.04% speed deviation
Run 1/3 - requested=16.63mm (at speed=3.31mm/s, flow=7.96mm³/s), measured=16.87mm in 5.03 seconds (at speed=3.33mm/s, flow=8.01mm³/s) = 0.12% speed deviation
Run 2/3 - requested=16.63mm (at speed=3.31mm/s, flow=7.96mm³/s), measured=16.41mm in 5.03 seconds (at speed=3.36mm/s, flow=8.08mm³/s) = 1.05% speed deviation
Run 3/3 - requested=16.63mm (at speed=3.31mm/s, flow=7.96mm³/s), measured=16.82mm in 5.14 seconds (at speed=3.37mm/s, flow=8.10mm³/s) = 1.21% speed deviation
Run 1/3 - requested=14.55mm (at speed=2.90mm/s, flow=6.97mm³/s), measured=14.72mm in 5.03 seconds (at speed=2.90mm/s, flow=6.97mm³/s) = 0.45% speed deviation
Run 2/3 - requested=14.55mm (at speed=2.90mm/s, flow=6.96mm³/s), measured=14.54mm in 5.03 seconds (at speed=2.95mm/s, flow=7.10mm³/s) = 1.43% speed deviation
Run 3/3 - requested=14.55mm (at speed=2.90mm/s, flow=6.98mm³/s), measured=14.40mm in 5.03 seconds (at speed=2.96mm/s, flow=7.12mm³/s) = 1.76% speed deviation
Run 1/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=12.57mm in 5.03 seconds (at speed=2.54mm/s, flow=6.11mm³/s) = 1.88% speed deviation
Run 2/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=12.48mm in 5.03 seconds (at speed=2.48mm/s, flow=5.97mm³/s) = 0.52% speed deviation
Run 3/3 - requested=12.47mm (at speed=2.48mm/s, flow=5.96mm³/s), measured=12.66mm in 5.03 seconds (at speed=2.51mm/s, flow=6.03mm³/s) = 0.48% speed deviation
Run 1/3 - requested=10.39mm (at speed=2.06mm/s, flow=4.96mm³/s), measured=10.19mm in 5.03 seconds (at speed=2.03mm/s, flow=4.89mm³/s) = 2.16% speed deviation
Run 2/3 - requested=10.39mm (at speed=2.06mm/s, flow=4.96mm³/s), measured=10.51mm in 5.03 seconds (at speed=2.09mm/s, flow=5.03mm³/s) = 0.60% speed deviation
Run 3/3 - requested=10.39mm (at speed=2.06mm/s, flow=4.96mm³/s), measured=10.42mm in 5.03 seconds (at speed=2.09mm/s, flow=5.02mm³/s) = 0.38% speed deviation
```

</details>

## Summary

| Extruder         | Weight | Measured max flow |
| :--------------- | :----- | :---------------- |
| Miró             | 58.4 g | 11.99mm³/s        |
| Dletgbs          | 50.1 g | 20.0mm³/s         |
| ProtoXtruderNX   | 49.3 g | 20.0mm³/s         |
| ProtoXtruder     | 47.8 g | 23.0mm³/s         |
| Tsunami 0.9      | 87.3 g | 19.0mm³/s         |
| ProtoXtruder 2.1 | 43.4 g | 23.0mm³/s         |

## To be continued

Tests and results will be split into a few posts; all posts will be summarized and placed on a [continuously evolving separate page]({{ '/extruderflows/' | relative_url }}).

Now comes the hardest part — creating prints to assess print quality.
