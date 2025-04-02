# variables

## Example
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/variables/uiflow_block_variables_example.svg">
Create variable

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

date = None

from numbers import Number

date = 10
date = (date if isinstance(date, Number) else 0) + 1
```

## API
- Assign values to variables
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/variables/uiflow_block_variables_set.svg">

```python
date = 10
```
<br><br>
- Modify the current variable, the input parameter is the modified size (e.g. +10, -10), can be an expression. If the variable value is not of type number, the result of the input parameter is assigned to the current variable.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/variables/uiflow_block_math_change.svg">

```python
date = (date if isinstance(date, Number) else 0) + (0 + 1)
```
<br><br>
- Perform value assignment
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/variables/uiflow_block_variables_get.svg">


