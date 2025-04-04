# Functions

## Example

Define two functions that take parameters for simple arithmetic operations

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Functions/uiflow_block_example.svg"> 

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

x = None
y = None
result = None

# Describe this function...
def func(x, y):
  global result
  if x < y:
    print(x + y)
  else:
    print(x - y)

# Describe this function...
def mathfunc(y, x):
  global result
  if x < 0:
    return y - x
  return x + y

func(2, 3)
result = mathfunc(10, 5)
```

## API
<br><br>
- Create a function that can be configured with parameters and the function does not return a value
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Functions/uiflow_block_procedures_defnoreturn.svg"> 

```python
def func(x, y):
  global result
  if x < y:
    print(x + y)
  else:
    print(x - y)
```

<br><br>
- Create a function that can be configured with parameters and the function does return a value
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Functions/uiflow_block_procedures_defreturn.svg"> 

```python
def mathfuc(y, x):
  global result
  return x + y
```

<br><br>
- Perform a simple if logic operation within the function, end the function operation, and return a value
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Functions/uiflow_block_procedures_ifreturn.svg"> 

```python
if x < 0:
    return y - x
```


