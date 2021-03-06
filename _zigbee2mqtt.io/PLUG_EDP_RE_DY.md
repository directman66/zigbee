---
model: PLUG EDP RE:DY
vendor: EDP
title: re:dy plug
category:
supports: on/off, power measurement
image: /assets/images/devices/PLUG-EDP-RE-DY.jpg
zigbeemodel: 
compatible: [z2m]
mlink: 
link: 
link2: 
link3: 
---
### Pairing
Factory reset the plug (hold the switch button for >10sec). After resetting the switch will automatically connect. 
{% raw %}
```yaml
switch:
  - platform: "mqtt"
    state_topic: "zigbee2mqtt/<FRIENDLY_NAME>"
    availability_topic: "zigbee2mqtt/bridge/state"
    payload_off: "OFF"
    payload_on: "ON"
    value_template: "{{ value_json.state }}"
    command_topic: "zigbee2mqtt/<FRIENDLY_NAME>/set"

sensor:
  - platform: "mqtt"
    state_topic: "zigbee2mqtt/<FRIENDLY_NAME>"
    availability_topic: "zigbee2mqtt/bridge/state"
    unit_of_measurement: "W"
    icon: "mdi:factory"
    value_template: "{{ value_json.power }}"

sensor:
  - platform: "mqtt"
    state_topic: "zigbee2mqtt/<FRIENDLY_NAME>"
    availability_topic: "zigbee2mqtt/bridge/state"
    unit_of_measurement: "-"
    value_template: "{{ value_json.linkquality }}"
```
{% endraw %}


