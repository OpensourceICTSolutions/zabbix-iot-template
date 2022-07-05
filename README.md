# zabbix-iot-template

Template as used in Zabbix blog post: 



#Template documentation

# IOT_temperature

## Macros used

|Name|Description|Default|Type|
|----|-----------|-------|----|
|{$MQTT_PORT}|<p>-</p>|`8883`|Text macro|
|{$MQTT_PROTOCOL}|<p>-</p>|`tls`|Text macro|
|{$MQTT_TOPIC}|<p>-</p>|`#`|Text macro|
|{$MQTT_URL}|<p>-</p>|`eu1.cloud.thethings.network`|Text macro|
|{$TTN_API_TOKEN}|<p>-</p>|`<TOKEN>`|Text macro|
|{$TTN_USER}|<p>-</p>|`<USER>`|Text macro|
## Template links

There are no template links in this template.

## Discovery rules

|Name|Description|Type|Key and additional info|
|----|-----------|----|----|
|discover sensors|<p>-</p>|`Dependent item`|disc.sensors<p>Update: 0</p>|
## Items collected

|Name|Description|Type|Key and additional info|
|----|-----------|----|----|
|mqtt master item|<p>-</p>|`Zabbix agent (active)`|mqtt.get[{$MQTT_PROTOCOL}://{$MQTT_URL}:{$MQTT_PORT},{$MQTT_TOPIC},{$TTN_USER},{$TTN_API_TOKEN}]<p>Update: 0</p>|
|Battery status of {#SENSOR}|<p>-</p>|`Dependent item`|bat.stat[{#SENSOR}]<p>Update: 0</p><p>LLD</p>|
|Battery voltage of {#SENSOR}|<p>-</p>|`Dependent item`|bat.voltage[{#SENSOR}]<p>Update: 0</p><p>LLD</p>|
|Humidity of  {#SENSOR}|<p>-</p>|`Dependent item`|humidity[{#SENSOR}]<p>Update: 0</p><p>LLD</p>|
|External temperature of {#SENSOR}|<p>-</p>|`Dependent item`|temp.extern[{#SENSOR}]<p>Update: 0</p><p>LLD</p>|
|Internal temperature of {#SENSOR}|<p>-</p>|`Dependent item`|temp.intern[{#SENSOR}]<p>Update: 0</p><p>LLD</p>|
## Triggers

There are no triggers in this template.
