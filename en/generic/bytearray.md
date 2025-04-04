# Bytearray

bytearray is a built-in mutable sequence type in Python for working with byte data. It is similar to the bytes type, but differs in that bytearray is mutable, whereas bytes is immutable. bytearray is very useful when working with binary data, especially if the data needs to be modified. It combines the mutability of lists with the efficient storage of byte strings, making it a flexible and powerful tool.

## Example

Creates a bytearray, and adds, removes, and decodes elements within it

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/bytearray/uiflow_block_bytearray_example.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

bytes2 = None

bytes2 = bytearray(5)
bytes2[0] = 104
bytes2[1] = 101
bytes2[2] = 108
bytes2[3] = 108
bytes2[4] = 111
bytes2.append(33)
print(bytes2.decode(bytes2))
print(bytes2[5])
```

## API
- Creates a bytearray of the specified length
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/bytearray/uiflow_block_variables_set.svg">

```python
bytes2 = bytearray(5)
```

<br><br>
- bytearray Specify index assignment
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/bytearray/uiflow_block_bytearray_setIndex.svg">

```python
bytes2[0] = 104
```

<br><br>
- Adds a byte to the end of the bytearray
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/bytearray/uiflow_block_bytearray_append.svg">

```python
bytes2.append(33)
```

<br><br>
- bytearray string decoding
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/bytearray/uiflow_block_bytearray_decode.svg">

```python
print(bytes2.decode('utf-8'))
```


