# Azure Classic

#>Creating Products and Devices | Please complete the creation of products and devices via [Azure IoT Center](https://learn.microsoft.com/zh-cn/azure/iot-hub/create-hub?tabs=portal) before using the UIFlow Azure Classic.

## Example

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/azure_classic/uiflow_block_azure_example.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
from IoTcloud.Azure import IoT_Hub
import json
import time
import unit

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)
env3_0 = unit.get(unit.ENV3, unit.PORTA)

msg = None
fun_msg = None
data = None
status = None
humid_data = None
temp_data = None

label0 = MCLabel('label0', x=27, y=53, color=0x000, font=FONT_MONT_14, parent=None)
label3 = MCLabel('label1', x=128, y=40, color=0x000, font=FONT_MONT_14, parent=None)
label7 = MCLabel('label1', x=147, y=90, color=0x000, font=FONT_MONT_14, parent=None)
label4 = MCLabel('label1', x=219, y=53, color=0x000, font=FONT_MONT_14, parent=None)

def azure_desired_cb(payload):
  global msg, fun_msg, data, status, humid_data, temp_data
  msg = payload
  label0.set_text(str(msg))

def azure_direct_rgb(payload, rid):
  global msg, fun_msg, data, status, humid_data, temp_data
  fun_msg = payload
  label0.set_text(str(fun_msg))
  if '"ON"' == fun_msg:
    label7.set_text('ON')
    rgb.setColorAll(0xffffff)
    azure.update_twin_reported_properties(rgb='ON')
    status = 204
  elif '"OFF"' == fun_msg:
    label7.set_text('OFF')
    rgb.setColorAll(0x000000)
    azure.update_twin_reported_properties(rgb='OFF')
    status = 204
  else:
    status = 400

  azure.response_direct_method(data, rid, body='success')

def azure_C2D_cb(msg_data):
  global msg, fun_msg, data, status, humid_data, temp_data
  msg = msg_data
  label0.set_text(str(msg))
  pass

azure = IoT_Hub(connection_string='HostName=MC4.0-iot.azure-devices.net;DeviceId=…')
azure.subscribe_twin_desired_response(azure_desired_cb)
azure.subscribe_direct_method('rgb', azure_direct_rgb)
azure.subscribe_C2D_message(azure_C2D_cb)
azure.start()
label0.set_text(str(azure.retrieve_twin_properties()))
while True:
  humid_data = env3_0.humidity
  temp_data = env3_0.temperature
  label3.set_text(str(temp_data))
  label4.set_text(str(humid_data))
  data = {temp:temp_data,humid:humid_data}
  azure.publish_D2C_message(str((json.dumps(data))))
  wait(5)
  wait_ms(2)
```


## API
- Initializing Azure IoT Central client information
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/azure_classic/uiflow_block_azure_init_central.svg">

```python
from IoTcloud.Azure import IoT_Central
azure = IoT_Central(scope_id='', device_id='', device_key='')
```

<br><br>
- Initializing Azure IoT Hub client information
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/azure_classic/uiflow_block_azure_init_iothub.svg">

```python
from IoTcloud.Azure import IoT_Hub
azure = IoT_Hub(connection_string='')
```

<br><br>
- Start client connect
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/azure_classic/uiflow_block_azure_start.svg">

```python
azure.start()
```


<br><br>
- publish messages
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/azure_classic/uiflow_block_azure_publish.svg">

```python
azure.publish_D2C_message(str(''))
```


<br><br>
- subscribe messages
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/azure_classic/uiflow_block_azure_sub.svg">

```python
def azure_C2D_cb(msg_data):
  msg = msg_data
  pass

azure.subscribe_C2D_message(azure_C2D_cb)
```



<br><br>
- report device twin properties
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/azure_classic/uiflow_block_azure_retrieve_twin_property.svg">

```python
azure.update_twin_reported_properties(key1='value',key2='value')
```



<br><br>
- subscribe direct_method messages 
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/azure_classic/uiflow_block_azure_sub_direct.svg">

```python
def azure_direct_fun(payload, rid):
  global methodmsg
  methodmsg = payload

  azure.response_direct_method(0, rid, body='')

```


<br><br>
- desired device twin callback
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/azure_classic/uiflow_block_azure_sub_twin_desired.svg">

```python
def azure_desired_cb(payload):
  msg = payload

azure.subscribe_twin_desired_response(azure_desired_cb)
```


<br><br>
- retrieve device twin properties
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/azure_classic/uiflow_block_azure_update_property.svg">

```python
azure.retrieve_twin_properties()
```



