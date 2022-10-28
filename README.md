## Tuya 16A Plug WG-08 - ESP8285/TYWE2S -> Flash ESPHome

![Plug](https://github.com/peca2345/Tuya-16A-Plug-WG-08---flash-FW-ESP8285/blob/main/IMG/Tuya16APlug.png?raw=true)

![Pinout](https://github.com/peca2345/Tuya-16A-Plug-WG-08---flash-FW-ESP8285/blob/main/IMG/esp8285_pinout2.png?raw=true)

![UART](https://github.com/peca2345/Tuya-16A-Plug-WG-08---flash-FW-ESP8285/blob/main/IMG/esp8285_uart2.png?raw=true)

![WIRING](https://github.com/peca2345/Tuya-16A-Plug-WG-08---flash-FW-ESP8285/blob/main/IMG/IMG_20221028_195522.jpg?raw=true)

![GPIO0](https://github.com/peca2345/Tuya-16A-Plug-WG-08---flash-FW-ESP8285/blob/main/IMG/IMG_20221028_195537.jpg?raw=true)

## ESPHome code
```
binary_sensor:
  - platform: gpio
    id: button
    name: Button
    pin:
      number: GPIO13
      mode: INPUT_PULLUP
      inverted: True
    on_press:
      - switch.toggle: relay      
      - switch.toggle: LED_blue 

switch:
  - platform: gpio
    id: LED_blue
    name: LED_blue
    pin: GPIO4
    inverted: True

  - platform: gpio
    id: LED_red
    name: LED_red
    pin: GPIO5
    inverted: True

  - platform: gpio
    id: relay
    name: relay
    pin: GPIO12

```
