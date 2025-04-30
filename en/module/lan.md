# Module13.2 LAN

## Example

> Connect to the MQTT server through the LAN module, subscribe to and publish messages, and poll downstream messages to control the device status (e.g., controlling the relay switch).

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_lan_demo.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import module

import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

lan = module.get(module.LAN_MODULE)

lan.lan_init(18, 23, 19, 5, 0, 35)
print('Lan Init')
wait(1.5)
lan.mqtt_config('mqtt.makerandcoder.com', 1883, 'mc40mqttid', '', '', 120)
print('Mqtt Confgured')
wait(1.5)
lan.mqtt_connect()
print('Connect Server')
wait(1.5)
lan.mqtt_subscribe('makerandcoder/relay', module_lan_mqtt_cb, 0)
while True:
  lan.mqtt_publish('makerandcoder/relay', 'ON', 0)
  wait(1.5)
  lan.mqtt_poll_loop()
  if False:
    print('ON')
  else:
    print('OFF')
  wait_ms(2)
```
<br><br>
## API
- Configure LAN TCP or UDP connection, specify the socket type (TCP or UDP), port number, and device type (server or client).
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_available_packet.svg">

```python
lan.is_available_packet(1)
```

<br><br>
- Fetch data from the server by specifying a topic and token.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_config.svg">

```python
lan.tcp_udp_config('', 0, 1, 1)
```

<br><br>
- uiflow_block_module_lan_ezdata_async_get_value
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_ezdata_async_get_value.svg">

```python
lan.get_ezdata(ezdata_get_AlUvNcb, 'GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '')
```

<br><br>
- uiflow_block_module_lan_ezdata_remove
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_ezdata_remove.svg">

```python
lan.remove_ezdata('GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '')
```

<br><br>
- uiflow_block_module_lan_ezdata_save
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_ezdata_save.svg">

```python
lan.set_ezdata('GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '', '', 0)
```

<br><br>
- uiflow_block_module_lan_get_data
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_get_data.svg">

```python
req.text
```

<br><br>
- uiflow_block_module_lan_get_if_config
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_get_if_config.svg">

```python
lan.get_if_config()
```

<br><br>
- uiflow_block_module_lan_get_status_code
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_get_status_code.svg">

```python
req.status_code
```

<br><br>
- uiflow_block_module_lan_http_request
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_http_request.svg">

```python
try:
  req = lan.http_request(method='GET', url='', headers={})
  gc.collect()
  req.close()
except:
  pass
```

<br><br>
- uiflow_block_module_lan_init
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_init.svg">

```python
lan.lan_init(18, 23, 19, 5, 0, 35)
```

<br><br>
- uiflow_block_module_lan_local_ip
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_local_ip.svg">

```python
lan.local_ip()
```

<br><br>
- uiflow_block_module_lan_mqtt_check_connection
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_mqtt_check_connection.svg">

```python
lan.mqtt_is_connect()
```

<br><br>
- uiflow_block_module_lan_mqtt_connect
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_mqtt_connect.svg">

```python
lan.mqtt_connect()
```

<br><br>
- uiflow_block_module_lan_mqtt_disconnect
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_mqtt_disconnect.svg">

```python
lan.mqtt_disconnect()
```

<br><br>
- uiflow_block_module_lan_mqtt_init
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_mqtt_init.svg">

```python
lan.mqtt_config('mqtt.makerandcoder.com', 1883, '', '', '', 120)
```

<br><br>
- uiflow_block_module_lan_mqtt_poll
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_mqtt_poll.svg">

```python
lan.mqtt_poll_loop()
```

<br><br>
- uiflow_block_module_lan_mqtt_publish
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_mqtt_publish.svg">

```python
lan.mqtt_publish('', '', 0)
```

<br><br>
- uiflow_block_module_lan_mqtt_sub
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_mqtt_sub.svg">

```python
lan.mqtt_subscribe('', module_lan_mqtt_cb, 0)
```

<br><br>
- uiflow_block_module_lan_mqtt_sub_cb
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_mqtt_sub_cb.svg">

```python
def module_lan_mqtt_cb(lan_mq_topic, lan_mq_payload):
  global ezdata_value1, lan_topic, lan_msg
  lan_topic = lan_mq_topic
  lan_msg = lan_mq_payload
  pass
```

<br><br>
- uiflow_block_module_lan_remote_ip
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_remote_ip.svg">

```python
lan.remote_ip()
```

<br><br>
- uiflow_block_module_lan_set_ifconfig
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_set_ifconfig.svg">

```python
lan.set_if_config('192.168.1.100', '255.255.255.0', '192.168.1.1', '8.8.8.8')
```

<br><br>
- uiflow_block_module_lan_socket_close
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_socket_close.svg">

```python
lan.socket_close()
```

<br><br>
- uiflow_block_module_lan_tcp_receive_packet
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_tcp_receive_packet.svg">

```python
lan.tcp_receive_packet(0)
```

<br><br>
- uiflow_block_module_lan_tcp_send_packet
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_tcp_send_packet.svg">

```python
lan.tcp_send_packet('1234')
```

<br><br>
- uiflow_block_module_lan_udp_receive_packet
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_udp_receive_packet.svg">

```python
lan.udp_receive_packet(0)
```

<br><br>
- uiflow_block_module_lan_udp_send_packet
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lan/uiflow_block_module_lan_udp_send_packet.svg">

```python
lan.udp_send_packet('', 0, '')
```


