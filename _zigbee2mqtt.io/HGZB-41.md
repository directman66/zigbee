---
model: HGZB-41
vendor: Nue / 3A 
title: Smart one gang wall switch
category:
supports: on/off
image: /assets/images/devices/HGZB-41.jpg
mlink: 
link: 
link2: 
link3: 

---### Pairing
Reset of device is done by holding button for 20 secs until it starts to flash green. It will now automatically pair. {% raw %}
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
    unit_of_measurement: "-"
    value_template: "{{ value_json.linkquality }}"
```
{% endraw %}


