# Map

## Example 

map function is a common built-in function or method in many programming languages. It is mainly used for iterable objects. Here is how to use map function

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Map/uiflow_block_example.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

data = None

data = {'a':1,'b':2,'c':'3'}
print('a' in data.keys())
print(data['b'])
data['d'] = '4'
data['a'] = '11'
data.pop('b')
data.clear()
```

## API
- Set key-value pairs in a dictionary
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Map/uiflow_block_set_map_key.svg">

```python
date['a'] = '11'
```

<br><br>
- Check if a key exists
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Map/uiflow_block_get_map_in.svg">

```python
print('a' in date.keys())
```

<br><br>
- Add a key-value pair to a dictionary
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Map/uiflow_block_add_map_key.svg">

```python
date['d'] = '4'
```

<br><br>
- Delete a specified key
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Map/uiflow_block_delete_map_key.svg">

```python
date.pop('b')
```

<br><br>
- Retrieve the value of a key
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Map/uiflow_block_get_map_key.svg">

```python
print(date['b'])
```

<br><br>
- Clear the dictionary
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Map/uiflow_block_map_clear.svg">

```python
date.clear()
```

<br><br>
- Establish key-value pairs
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Map/uiflow_block_map_on_loop.svg">

```python
date = {'a':1,'b':2,'c':'3'}
```


