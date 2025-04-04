# EzData

EzData is an IoT cloud data storage service provided by MC4.0, allowing different devices to insert or retrieve data into a storage queue using a unique token, enabling data sharing across devices.

<img src="https://static-cdn.m5stack.com/resource/docs/static/image/iotservice/ezdata/ezdata_01.webp" width="70%">

## Example

<img src="https://makerandcoder.com/MCLab/blockly/ezdata/uiflow_block_example.svg" width="70%">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
from flow import ezdata
import wifiCfg

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

i = None

wifiCfg.autoConnect(lcdShow=False)

while True:
  ezdata.setData('6ijRMmiFRdO2tVfFIbNpy6PN1sRvFmsy', 'my_topic', 'Hello EzData')
  print(ezdata.getData('6ijRMmiFRdO2tVfFIbNpy6PN1sRvFmsy', 'my_topic'))
  for i in range(11):
    ezdata.setData('6ijRMmiFRdO2tVfFIbNpy6PN1sRvFmsy', 'my_list', i)
  print(ezdata.getData('6ijRMmiFRdO2tVfFIbNpy6PN1sRvFmsy', 'my_list', 0, 50))
  ezdata.removeData('6ijRMmiFRdO2tVfFIbNpy6PN1sRvFmsy', 'my_topic')
  print(ezdata.getCurrentISODateTime())
  wait_ms(2)
```

## API
- Save Data to the Head of a Specified Topic Queue
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ezdata/uiflow_block_ezdata_set_key_with_token.svg" width="70%">

```python
ezdata.setData('6ijRMmiFRdO2tVfFIbNpy6PN1sRvFmsy', 'my_topic', 'Hello EzData')
```

<br><br>
- Retrieve a Data Item from the Head of a Specified Topic Queue
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ezdata/uiflow_block_ezdata_get_key_with_token.svg" width="70%">

```python
print(ezdata.getData('6ijRMmiFRdO2tVfFIbNpy6PN1sRvFmsy', 'my_topic'))
```

<br><br>
- Save Data to the Head of a Specified Data List
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ezdata/uiflow_block_ezdata_add_value_with_token.svg" width="70%">

```python
ezdata.addToList('6ijRMmiFRdO2tVfFIbNpy6PN1sRvFmsy', 'my_list', i)
```

<br><br>
- Retrieve a Set of Data from a Specified Data List, with the advantage of list storage being able to specify an offset from the head of the list and retrieve multiple data items at once. Parameters include:
- list: Name of the list (string)
- offset: Offset from the head of the list
- count: Number of data items to retrieve
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ezdata/uiflow_block_ezdata_get_list_with_token.svg" width="70%">

```python
print(ezdata.getData('6ijRMmiFRdO2tVfFIbNpy6PN1sRvFmsy', 'my_list', 0, 50))
```

<br><br>
- Delete a Topic or List and Clear Queue Data
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ezdata/uiflow_block_ezdata_remove_key_with_token.svg" width="70%">

```python
ezdata.removeData('6ijRMmiFRdO2tVfFIbNpy6PN1sRvFmsy', 'my_topic')
```

<br><br>
- Get Current ISO Date and Time
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ezdata/uiflow_block_ezdata_get_iso_date.svg" width="70%">

```python
print(ezdata.getCurrentISODateTime())
```

<br><br>
- Asynchronous Operation: Save data to the head of a specified topic queue
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ezdata/uiflow_block_ezdata_async_set_value.svg" width="70%">

```python
ezdata.setDataAsync(ezdata_set_NdmNNcb, ezdata_set_fail_NdmNNcb, '6ijRMmiFRdO2tVfFIbNpy6PN1sRvFmsy', 'my_topic', 'Hello EzData')
```
<br><br>
- Asynchronous Operation: Save data to the head of a specified data list
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ezdata/uiflow_block_ezdata_async_set_list_value.svg" width="70%">

```python
ezdata.addToListAsync(ezdata_set_iQCwDcb, ezdata_set_fail_iQCwDcb, '6ijRMmiFRdO2tVfFIbNpy6PN1sRvFmsy', 'my_list', i)
```

<br><br>
- Asynchronous Operation: Retrieve a data item from the head of a specified topic queue
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ezdata/uiflow_block_ezdata_async_get_value.svg" width="70%">

```python
ezdata.getDataAsync(ezdata_get_iRBYXcb, ezdata_get_fail_iRBYXcb, '6ijRMmiFRdO2tVfFIbNpy6PN1sRvFmsy', 'my_topic')
```

<br><br>
- Asynchronous Operation
- Retrieve a Set of Data from a Specified Data List, with the advantage of list storage being able to specify an offset from the head of the list and retrieve multiple data items at once. Parameters include:
- list: Name of the list (string)
- offset: Offset from the head of the list
- count: Number of data items to retrieve
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ezdata/uiflow_block_ezdata_async_get_list_value.svg" width="70%">

```python
ezdata.getDataAsync(ezdata_get_rfWJMcb, ezdata_get_fail_rfWJMcb, '6ijRMmiFRdO2tVfFIbNpy6PN1sRvFmsy', 'my_list', 0, 50)
```

<br><br>
- Asynchronous Operation: Delete a topic or list and clear queue data
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ezdata/uiflow_block_ezdata_async_remove.svg" width="70%">

```python
ezdata.removeDataAsync(ezdata_remove_KcMAbcb, ezdata_remove_fail_KcMAbcb, '6ijRMmiFRdO2tVfFIbNpy6PN1sRvFmsy', '')
```
<br><br>
- Asynchronous Operation: Get current ISO date and time
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ezdata/uiflow_block_ezdata_async_get_iso_date.svg" width="70%">

```python
ezdata.getCurrentISODateTimeAsync(ezdata_get_ESdHGcb, ezdata_get_fail_ESdHGcb)
```



#>Notes:<br>1. All operations above rely on a unique token, which remains fixed within the same browser environment. Please copy the token before use.<br>2.If no data operations are performed within six months, the data queue corresponding to that token will be emptied.<br>3. Data is sorted in descending order based on insertion time (with the last inserted data at the head of the list), and data accumulates over time.
