# ESPHome, Let's build a pool sensor, Part 3

In this part we will add a 1 Channel Relay Module (DC 5V) to operate Skimmer

## Bill of Materials
- A 1 Channel Relay Module (DC 5V) - https://www.amazon.co.uk/dp/B09M62VCGX?ref=ppx_yo2ov_dt_b_product_details&th=1

## Code
### GPIO Switch
- gpio_switch.yml - https://esphome.io/components/switch/gpio.html
- restore_mode - https://esphome.io/components/switch/index.html#config-switch
- restore_mode (Optional): Control how the switch attempts to restore state on bootup. NOTE : Not all components consider restore_mode. Check the documentation of the specific component to understand how this feature works for a particular component or device. For restoring on ESP8266s, also see restore_from_flash in the esp8266 section.
-- RESTORE_DEFAULT_OFF - Attempt to restore state and default to OFF if not possible to restore.
-- RESTORE_DEFAULT_ON - Attempt to restore state and default to ON.
-- RESTORE_INVERTED_DEFAULT_OFF - Attempt to restore state inverted from the previous state and default to OFF.
-- RESTORE_INVERTED_DEFAULT_ON - Attempt to restore state inverted from the previous state and default to ON.
-- ALWAYS_OFF (Default) - Always initialize the switch as OFF on bootup.
-- ALWAYS_ON - Always initialize the switch as ON on bootup.
-- DISABLED - Does nothing and leaves it up to the downstream platform component to decide. For example, the component could read hardware and determine the state, or have a specific configuration option to regulate initial state.
Unless a specific platform defines another default value, the default is ALWAYS_OFF.

## Relay description
- Description:
AEDIKO 4pcs Relay Module DC 5V 1 Channel Relay Board with Optocoupler Isolation Support High or Low Level Trigger

- About this item:
5V Relay Module:
-- Working Voltage: DC 5V;
-- Maximum Load: AC 250V/10A, DC 30V/10A;
-- Trigger Current of Opto-Isolator: 5mA
Fault-Tolerant Design: Fault Tolerant Design, Even if the Control Line is Broken, the Relay will not Operate;All Interfaces of Relay can be Wired Out Through the Terminals Directly,Normally Open and Normally Closed
-- Optocoupler Isolation: 1 Channel Relay Board use Optocoupler Isolation that has Strong Driving Ability and Stable Performance,The Isolation Circuit Prevent Damages to I / O Port by Relay Switch Current
-- Jumper Design: The Relay Module has a Jumper That You Can Set Rather the Unit State Changes with High or Low Signal. Has Screw Terminals for Relay (NC,C,NO) and for Input; Coil +, Coil - and Trigger.
-- Wide Application: DC 5V Relay Module Works Well with ARM /PIC /AVR /MCU/Raspberry/CNC Machine/ PS4 etc.

