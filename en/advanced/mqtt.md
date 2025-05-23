# MQTT

#>What is MQTT? |(Message Queuing Telemetry Transport (MCT), is a "lightweight" communication protocol based on publish/subscribe (publish/subscribe) model. The protocol is built on the TCP/IP protocol, as a low overhead, low bandwidth consumption of instant messaging protocol, so that it has a wide range of applications in the Internet of Things, small devices, mobile applications and so on.

## Example

Connects to MQTT server for subscription and topic publishing.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/mqtt/uiflow_block_mqtt_example.svg"> 


```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
from mcmqtt import MCmqtt
import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

def fun__(topic_data):
  # global params
  print('topic: /dev/sub received:')
  print(topic_data)
  pass

mcmqtt = MCmqtt('id_123456', 'broker.emqx.io', 1883, 'user_123456', 'pwd_123456', 20)
mcmqtt.subscribe(str(''), fun__)
print('mqtt connecting....')
mcmqtt.set_last_will(str('/dev/last_will'),str('device disconnect'))
mcmqtt.start()
print('mqtt connected')
while True:
  mcmqtt.publish(str('/dev/pub'), str('Hello'), 0)
  wait(10)
  wait_ms(2)

```


## API
- Initialize MQTT client information.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/mqtt/uiflow_block_mqtt_set_client.svg"> 

```python
m5mqtt = M5mqtt('id_123456', 'broker.emqx.io', 1883, 'user_123456', 'pwd_123456', 20)

```


<br><br>
- If you wish to initialize the MQTTS connection, enable the SSL option and import the client certificate to the device via the `+` sign.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/mqtt/uiflow_block_mqtt_set_client_ssl.svg"> 

```python
m5mqtt = M5mqtt('id_123456', 'broker.emqx.io', 1883, 'user_123456', 'pwd_123456', 20, ssl = True, ssl_params = {'key': "/flash/res/certificate.pem.crt", 'cert': "/flash/res/private.pem.key"})
```
<br><br>
- Set the MQTT client last will message that the server will publish when the client disconnects abnormally. Note: The last will message needs to be configured before mqtt start connection.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/mqtt/uiflow_block_mqtt_set_last_will.svg"> 

```python
m5mqtt.set_last_will(str('/dev/last_will'),str('device disconnect'))
```


<br><br>
- Start connecting to the MQTT server
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/mqtt/uiflow_block_mqtt_start.svg"> 

```python
m5mqtt.start()
```

<br><br>
- Publish the specified topic information, as well as the configuration information QoS level
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/mqtt/uiflow_block_mqtt_publish.svg"> 

```python
m5mqtt.publish(str('/dev/pub'), str('Hello'), 0)
```


<br><br>
- Subscribe to topic messages and configure the corresponding callback function, which will be executed automatically when the topic message is received.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/mqtt/uiflow_block_mqtt_sub.svg"> 

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/mqtt/uiflow_block_mqtt_get_topic_data.svg"> 

```python
def fun__dev_sub_(topic_data):
  print(topic_data)
  pass

m5mqtt.subscribe(str('/dev/sub'), fun__dev_sub_)
```


