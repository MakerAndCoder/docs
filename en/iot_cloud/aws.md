# AWS

#>Creating Products and Devices | Please complete the creation of products and devices via [AWS Management Console](https://aws.amazon.com/) before using UIFlow AWS.

## Example

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/aws/uiflow_block_aws_example.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
from IoTcloud.AWS import AWS
import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

label0 = MCLabel('label0', x=134, y=111, color=0x000, font=FONT_MONT_14, parent=None)

def fun_subtopic_(topic_data):
  # global params
  label0.set_text(str(topic_data))
  pass

aws = AWS(things_name='MC4.0_Test', host='xxxxxxxxxxx-ats.iot.ap-southeast-1.amazonaws.com', port=8883, keepalive=60, cert_file_path='', private_key_path='')
aws.subscribe(str('subtopic'), fun_subtopic_)
aws.start()
while True:
  aws.publish(str('pubtopic'),str('hello'))
  wait(4)
  wait_ms(2)
```

## API


- Initialize client:
  - Click the Add button in the initialization block to import Device certificate + Private Key File, Note: The default key and certificate file name is too long, try to change it to a shorter string.
  - The things name is the name of the device we created, and it needs to match the name in the AWS Management Console.
  - Copy the Endpoint field from AWS Management Console->Settings and populate it with the HOST parameter.
  - For the port parameter we use the MQTT service port 8883
  - keepalive 60 
  - For more information on service ports please refer to [AWS Official Documentation](https://docs.aws.amazon.com/iot/latest/developerguide/protocols.html?icmpid=docs_iot_console).

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/aws/uiflow_block_aws_init.svg">


```python
from IoTcloud.AWS import AWS
aws = AWS(things_name='', host='', port=0, keepalive=0, cert_file_path='', private_key_path='')
```
<br /><br />

- Start client connect

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/aws/uiflow_block_aws_start.svg">

```python
aws.start()
```
<br /><br />

- publish messages

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/aws/uiflow_block_aws_publish.svg">

```python
aws.publish(topic,msg)
```
<br /><br />

- subtopic messages callback

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/aws/uiflow_block_aws_sub.svg">

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/aws/uiflow_block_aws_get_topic_data.svg">

```python
def fun_subtopic_(topic_data):
  # global params
  print(topic_data)
  pass

```


