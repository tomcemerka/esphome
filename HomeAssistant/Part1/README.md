# HA, Let's build a network rack and attach fans, Part 1

In this part we will cover adding 120mm Fans to Network rack

## Bill of Materials

- I bought a couple of 120mm USB Fans - https://www.amazon.co.uk/dp/B081RQRY3G?ref=ppx_yo2ov_dt_b_fed_asin_title
- Tecmojo 6U 450mm Deep Wall Mount Network Rack Enclosure - https://www.amazon.co.uk/dp/B0DBQWVKX3?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1
- Lms Data 6 Way Horizontal 13a Switched Power Distribution Unit (PDU) (or similar) - https://www.amazon.co.uk/dp/B0080OISQQ?ref=ppx_yo2ov_dt_b_fed_asin_title
- Couple of USB Plugs - https://www.amazon.co.uk/dp/B09B63LPRP?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1 (could be single usb socket only) 
- Couple of Tuya zigbee smart-plug model 'TS011F' or similar Smart plugs - https://www.amazon.co.uk/Monitoring-Assistant-Zigbee2MQTT-Repeater-Function/dp/B0F514V67X/ref=sr_1_8?dib=eyJ2IjoiMSJ9.xZ9zoEF2gdhZb5vjIP6P_mN9HidgEd_b7tWEkqTVvK3F5BSn7B9C2j54-AGsdRFxFQ9hAcooGrKpVN3LdwO3kMubeSdxwWdry2-F244W7lB6ICHFQWpukLb_NjksPvlyYoEwFTuDvYyv8mAsMF11njm8KSHFMdzSXesH5gvu7EHS311Gl8B4VKV4ovkWPXw7rRwZTFVTtKFowLoojLp6KAC1iMbYclbIfTDzFbTZ4X0CvkgV8-awP2iQQSl6DucweIEflYo1sa6KeY-361oygkx9s9NO6J_yfbtXNgRR988.Yf7YLLXXDd0rUhpMCpk8hyOEa4z9lrV6fTdT1EDpC1M&dib_tag=se&keywords=zigbee+socket+uk&qid=1748265895&sr=8-8 (or similar type)


## Assembly
- Assemble network rack
- Attach fans to the top of the network rack. There are dedicated fan mounting holes
- Mount network rack on the wall
- Plug in couple of zigbee smart-plugs into PDU
- Connect Fan1 to the first zigbee Smart plug
- Connect Fan2 to the second zigbee Smart plug
- Add Zigbee Smart plugs into Home Assistant and nme it as RackFan1, RackFan2 (or similar)

## Code
Let's integrate ESPHome Network Rack project with Home Assistant and create Automation to control fans

### Entities
- sensor.esphrack_inside_temperature - monitors rack inside temperature and provides results to HA every 30s
- switch.srvfan1 - switch that controls Smart Plug that in turn turns On/Off USB Fan1
- switch.srvfan2 - switch that controls Smart Plug that in turn turns On/Off USB Fan2

### Logic

If sensor.esphrack_inside_temperature >=29.9C
turn on switch.srvfan1

if sensor.esphrack_inside_temperature <29C
turn off switch.srvfan1

if sensor.esphrack_inside_temperature >34.9C
turn on switch.srvfan2

if sensor.esphrack_inside_temperature <35C
turn off switch.srvfan2

