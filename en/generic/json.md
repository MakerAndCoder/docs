# Json

## Example

JSON is a lightweight data interchange format, and here's how to use JSON functions


<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/JSON/uiflow_block_example.svg"> 

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
from libs.json_py import *
import json

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

data = None
json_object = None

data = py_2_json({'author':'Maker&Coder','people':100,'device':'MC4.0','number':'5'})
print(json.dumps(data))
print(get_json_keys(data))
print(get_json_key(data, 'number'))
print(get_json_values(data))
print(get_json_keys_len(data))
set_json_elements(data, 'people', 101)
set_json_elements(data, 'devicetwo', 'AICamera')
delete_json_elements(json_object, 'number')
print(json.dumps(data))
print(json.loads('{"string":"stack","number":100}'))
```

## API
- Convert (serialize) a Python object (such as a list or dictionary) into a JSON-formatted string
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/JSON/uiflow_block_dumps_json.svg"> 

```python
print(json.dumps(data))
```

<br><br>
- Add a key-value pair to a JSON object
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/JSON/uiflow_block_json_add_key_value.svg"> 

```python
set_json_elements(data, 'devicetwo', 'core2')
```

<br><br>
- Create a JSON object using key-value pairs
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/JSON/uiflow_block_json_create.svg"> 

```python
data = py_2_json({'author':'MC4.0','people':100,'device':'CoreS3','number':'5'})
```

<br><br>
- Delete a key-value pair from a JSON object based on the key
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/JSON/uiflow_block_json_del_key.svg"> 

```python
delete_json_elements(data, 'number')
```

<br><br>
- Get the value of a specified key from a JSON object
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/JSON/uiflow_block_json_get_key_value.svg"> 

```python
print(get_json_key(data, 'number'))
```

<br><br>
- Get all keys from a JSON object and return them as a list
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/JSON/uiflow_block_json_get_keys.svg"> 

```python
print(get_json_keys(data))
```

<br><br>
- Get the length of a JSON object (note: for dictionaries, it's the number of key-value pairs)
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/JSON/uiflow_block_json_get_keys_len.svg"> 

```python
print(get_json_keys_len(data))
```

<br><br>
- Get all values from a JSON object and return them as a list
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/JSON/uiflow_block_json_get_values.svg"> 

```python
print(get_json_values(data))
```

<br><br>
- Set the value of a corresponding key in a JSON object
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/JSON/uiflow_block_json_set_key_value.svg"> 

```python
set_json_elements(data, 'people', 101)
```

<br><br>
- Parse a string containing a valid JSON object
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/JSON/uiflow_block_variables_set.svg"> 

```python
print(json.loads('{"string":"stack","number":100}'))
```


