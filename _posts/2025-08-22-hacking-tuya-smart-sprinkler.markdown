---
layout: post
title:  "Hacking Tuya Smart sprinkler / irrigation controller"
date:   2025-08-25 12:10:00 +0100
categories: DIY zigbee smarthome esphome
tags: [DIY, zigbee, smarthome, esphome]
excerpt: "Making TUYA device cloudless and controll directly by ESPHom/HomeAssistant"
---

There are not many dedicated sprinkler controllers on the internet that can be integrated with Home Assistant. Moreover, most available electromagnetic valves use AC, which creates the problem of needing an additional power supply to get them working. Nowadays, you can buy DC coils (for example, Hunter makes some), but they are much more expensive.

## Solution used so far

Previously, I used a modified LILYGO T-Relay with an external WiFi antenna. It worked reliably, but as mentioned, it required a DC power supply for the T-Relay and AC for the coils. After a few years of reliable operation, I added another watering section to my garden. However, since I used a T-Relay with 4 relays and none were free anymore, I needed to find a new solution.

## New possible solutions

### Additional Relay

The ESP32 board has enough GPIOs to control many more relays, but due to the external DC PSU, I ran out of space in the hermetic box. Buying a new one was not an option because the old one was already too big.

### Design own PCB

Years ago, I designed my own PCBs, but now I’m older, lazier, and don’t have as much time. Like the previous proposal, this idea was also rejected.

## Find an Out-of-the-Box Solution

Solutions from big companies are usually very expensive and often cannot be integrated with Home Assistant.
After days of searching online, I was unable to find any suitable solution for controlling 24 ACV valves over ZigBee. Moreover, WiFi-based solutions are also limited to Tuya Cloud.

## Summary

It is very hard to find a solution that fits the needs of cloud-independent home automation.

## Experiment

During research for another project, I found that it’s possible to bypass Tuya Cloud using different tools, so I decided to buy a controller like the one shown below.

![alt](/pic/sprinkler/image.png)
*Device for experiment*

When it arrived, I decided to disassemble it. The front acrylic panel is glued with thin double-sided tape, so to remove it, you need to use a thin knife and carefully pry off the panel.

Inside, there is a CBU unit. After some research, I found that it can be flashed with ESPHome, so I decided to try it. I also found a place for a U.FL connector, so I used an external WiFi antenna because the device is located in a metal enclosure.

To flash the CBU unit, you have to solder cables or use a 3D-printed adapter called the [Tuya CBU Flashing Jig](https://www.printables.com/model/763948-tuya-cbu-flashing-jig)

These are the results of all those operations

![alt](/pic/sprinkler/1000014319.jpg){: .small-image}
*Flashing without jig*

![alt](/pic/sprinkler/1000014569.jpg){: .small-image}
*Mounted device*

## ESPHome

Now it was time for some reverse engineering and coding. I spent a few hours testing and tweaking the code, and here is the resulting configuration, which supports the controller’s LED indicators and touch buttons.

```yaml
esphome:
  name: "smart-sprinkler"
  friendly_name: "smart-sprinkler"

bk72xx:
  board: cbu

# Enable logging
logger:

# Enable Home Assistant API
api:
  encryption:
    key: ""

ota:
  - platform: esphome
    password: ""
# <= Full snipped in below collapsed section
```

<details markdown="1">

<summary>Full yaml code - too long to show on page</summary>

```yaml
esphome:
  name: "smart-sprinkler"
  friendly_name: "smart-sprinkler"

bk72xx:
  board: cbu

# Enable logging
logger:

# Enable Home Assistant API
api:
  encryption:
    key: ""

ota:
  - platform: esphome
    password: ""

wifi:
  ssid: !wifi_iot_ssid
  password: !wifi_iot_password

  # Enable fallback hotspot (captive portal) in case wifi connection fails
  ap:
    ssid: "Smart-sprinkler Fallback Hotspot"
    password: ""
  fast_connect: True


captive_portal:

# Configure shift registers
sn74hc595:
  - id: 'sn74hc595_hub'
    data_pin: GPIO9
    clock_pin: GPIO15
    latch_pin: GPIO17
    sr_count: 2
  - id: 'sn74hc595_relay_hub'
    data_pin: GPIO16
    clock_pin: GPIO22
    latch_pin: GPIO20
    sr_count: 2


output:
  - platform: gpio
    id: status_led_1
    pin:
      sn74hc595: sn74hc595_hub
      number: 0
      inverted: true

  - platform: template
    type: binary
    id: status_led_1_temp
    write_action:
      - while:
          condition:
            lambda: return (state > 0);
          then:
            - output.turn_on: status_led_1
            - delay: 500ms
            - output.turn_off: status_led_1
            - delay: 500ms
      - output.turn_off: status_led_1

  - platform: gpio
    id: status_led_2
    pin:
      sn74hc595: sn74hc595_hub
      number: 1
      inverted: true
  - platform: template
    type: binary
    id: status_led_2_temp
    write_action:
      - while:
          condition:
            lambda: return (state > 0);
          then:
            - output.turn_on: status_led_2
            - delay: 500ms
            - output.turn_off: status_led_2
            - delay: 500ms
      - output.turn_off: status_led_2

  - platform: gpio
    id: status_led_3
    pin:
      sn74hc595: sn74hc595_hub
      number: 2
      inverted: true
  - platform: template
    type: binary
    id: status_led_3_temp
    write_action:
      - while:
          condition:
            lambda: return (state > 0);
          then:
            - output.turn_on: status_led_3
            - delay: 500ms
            - output.turn_off: status_led_3
            - delay: 500ms
      - output.turn_off: status_led_3

  - platform: gpio
    id: status_led_4
    pin:
      sn74hc595: sn74hc595_hub
      number: 3
      inverted: true
  - platform: template
    type: binary
    id: status_led_4_temp
    write_action:
      - while:
          condition:
            lambda: return (state > 0);
          then:
            - output.turn_on: status_led_4
            - delay: 500ms
            - output.turn_off: status_led_4
            - delay: 500ms
      - output.turn_off: status_led_4

  - platform: gpio
    id: status_led_5
    pin:
      sn74hc595: sn74hc595_hub
      number: 4
      inverted: true
  - platform: template
    type: binary
    id: status_led_5_temp
    write_action:
      - while:
          condition:
            lambda: return (state > 0);
          then:
            - output.turn_on: status_led_5
            - delay: 500ms
            - output.turn_off: status_led_5
            - delay: 500ms
      - output.turn_off: status_led_5

  - platform: gpio
    id: status_led_6
    pin:
      sn74hc595: sn74hc595_hub
      number: 5
      inverted: true
  - platform: template
    type: binary
    id: status_led_6_temp
    write_action:
      - while:
          condition:
            lambda: return (state > 0);
          then:
            - output.turn_on: status_led_6
            - delay: 500ms
            - output.turn_off: status_led_6
            - delay: 500ms
      - output.turn_off: status_led_6

  - platform: gpio
    id: status_led_7
    pin:
      sn74hc595: sn74hc595_hub
      number: 6
      inverted: true
  - platform: template
    type: binary
    id: status_led_7_temp
    write_action:
      - while:
          condition:
            lambda: return (state > 0);
          then:
            - output.turn_on: status_led_7
            - delay: 500ms
            - output.turn_off: status_led_7
            - delay: 500ms
      - output.turn_off: status_led_7
  - platform: gpio
    id: status_led_8
    pin:
      sn74hc595: sn74hc595_hub
      number: 7
      inverted: true
  - platform: template
    type: binary
    id: status_led_8_temp
    write_action:
      - while:
          condition:
            lambda: return (state > 0);
          then:
            - output.turn_on: status_led_8
            - delay: 500ms
            - output.turn_off: status_led_8
            - delay: 500ms
      - output.turn_off: status_led_8
  - platform: gpio
    pin: 28
    id: led_wifi
    inverted: true

interval:
  - interval: 1s
    then:
      if:
        condition:
          wifi.connected:
        then:
          - output.turn_on: led_wifi
        else:
          - output.turn_off: led_wifi
  # Interval for closing cycle of choosing valves
  - interval: 120s
    then:
      if:
        condition:
          lambda: !lambda |-
            if (id(valve_id)){
              return true;
            }
            return false;
        then:
          lambda: !lambda |-
            id(recover_status_led).execute();
            id(valve_id) = 0;

# Valves configuratin
switch:
  - platform: gpio
    name: valve_1
    id: valve_1
    pin:
      sn74hc595: sn74hc595_relay_hub
      number: 0
    on_turn_on:
      - output.turn_on: status_led_1
    on_turn_off:
      - output.turn_off: status_led_1
  - platform: gpio
    name: valve_2
    id: valve_2
    pin:
      sn74hc595: sn74hc595_relay_hub
      number: 1
    on_turn_on:
      - output.turn_on: status_led_2
    on_turn_off:
      - output.turn_off: status_led_2
  - platform: gpio
    name: valve_3
    id: valve_3
    pin:
      sn74hc595: sn74hc595_relay_hub
      number: 2
    on_turn_on:
      - output.turn_on: status_led_3
    on_turn_off:
      - output.turn_off: status_led_3
  - platform: gpio
    name: valve_4
    id: valve_4
    pin:
      sn74hc595: sn74hc595_relay_hub
      number: 3
    on_turn_on:
      - output.turn_on: status_led_4
    on_turn_off:
      - output.turn_off: status_led_4
  - platform: gpio
    name: valve_5
    id: valve_5
    pin:
      sn74hc595: sn74hc595_relay_hub
      number: 4
    on_turn_on:
      - output.turn_on: status_led_5
    on_turn_off:
      - output.turn_off: status_led_5
  - platform: gpio
    name: valve_6
    id: valve_6
    pin:
      sn74hc595: sn74hc595_relay_hub
      number: 5
    on_turn_on:
      - output.turn_on: status_led_6
    on_turn_off:
      - output.turn_off: status_led_6
  - platform: gpio
    name: valve_7
    id: valve_7
    pin:
      sn74hc595: sn74hc595_relay_hub
      number: 6
    on_turn_on:
      - output.turn_on: status_led_7
    on_turn_off:
      - output.turn_off: status_led_7
  - platform: gpio
    name: valve_8
    id: valve_8
    pin:
      sn74hc595: sn74hc595_relay_hub
      number: 7
    on_turn_on:
      - output.turn_on: status_led_8
    on_turn_off:
      - output.turn_off: status_led_8
  - platform: gpio
    name: motor
    id: motor
    pin:
      number: 24


globals:
  # Variable used for switch case to choose valve using buttons
  - id: valve_id
    type: int
    restore_value: no
    initial_value: '0'


#Physical buttons configuration with actions
binary_sensor:
  - platform: gpio
    id: back
    pin:
      number: 7
      mode:
        input: true
        pullup: true
    on_press: 
      then:
        lambda: !lambda |-
          id(recover_status_led).execute();
          id(valve_id) = (id(valve_id) - 1);
          id(blink_status_led).execute();
  - platform: gpio
    id: forward
    pin:
      number: 6
      mode:
        input: true
        pullup: true
    on_press: 
      then:
        lambda: !lambda |-
          id(recover_status_led).execute();
          id(valve_id) = (id(valve_id) + 1);
          id(blink_status_led).execute();
  - platform: gpio
    id: play
    pin:
      number: 8
      mode:
        input: true
        pullup: true
    on_press: 
      then:
        script.execute: toogle_valve
  - platform: gpio
    id: config
    pin:
      number: 26
      mode:
        input: true
        pullup: true
    on_press: 
      then:
        lambda: !lambda |-
          id(recover_status_led).execute();
          id(valve_id) = 0;

script:
  # Restore previous status of led
  - id: recover_status_led
    then:
      lambda: !lambda |-
        switch (id(valve_id)){
          case 1:
            id(status_led_1_temp).turn_off();
            if (id(valve_1).state){
              id(status_led_1).turn_on();
            }
            break;
          case 2:
            id(status_led_2_temp).turn_off();
            if (id(valve_2).state){
              id(status_led_2).turn_on();
            }
            break;
          case 3:
            id(status_led_3_temp).turn_off();
            if (id(valve_3).state){
              id(status_led_3).turn_on();
            }
            break;
          case 4:
            id(status_led_4_temp).turn_off();
            if (id(valve_4).state){
              id(status_led_4).turn_on();
            }
            break;
          case 5:
            id(status_led_5_temp).turn_off();
            if (id(valve_5).state){
              id(status_led_5).turn_on();
            }
            break;
          case 6:
            id(status_led_6_temp).turn_off();
            if (id(valve_6).state){
              id(status_led_6).turn_on();
            }
            break;
          case 7:
            id(status_led_7_temp).turn_off();
            if (id(valve_7).state){
              id(status_led_7).turn_on();
            }
            break;
          case 8:
            id(status_led_8_temp).turn_off();
            if (id(valve_8).state){
              id(status_led_8).turn_on();
            }
            break;
        }
  # Blink single status led choosen using buttons
  - id: blink_status_led
    then:
      lambda: !lambda |-
        switch (id(valve_id)){
          case 1:
            id(status_led_1_temp).turn_on();
            break;
          case 2:
            id(status_led_2_temp).turn_on();
            break;
          case 3:
            id(status_led_3_temp).turn_on();
            break;
          case 4:
            id(status_led_4_temp).turn_on();
            break;
          case 5:
            id(status_led_5_temp).turn_on();
            break;
          case 6:
            id(status_led_6_temp).turn_on();
            break;
          case 7:
            id(status_led_7_temp).turn_on();
            break;
          case 8:
            id(status_led_8_temp).turn_on();
            break;
          default:
            id(valve_id) = 0;
            break;
        }

  - id: toogle_valve
    then:
      lambda: !lambda |-
        switch (id(valve_id)){
          case 1:
            id(valve_1).toggle();
            break;
          case 2:
            id(valve_2).toggle();
            break;
          case 3:
            id(valve_3).toggle();
            break;
          case 4:
            id(valve_4).toggle();
            break;
          case 5:
            id(valve_5).toggle();
            break;
          case 6:
            id(valve_6).toggle();
            break;
          case 7:
            id(valve_7).toggle();
            break;
          case 8:
            id(valve_8).toggle();
            break;
        }

```

</details>

## The end
