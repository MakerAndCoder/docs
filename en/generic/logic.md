# Logic

## Example

Logical processing functions are used

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Logic/uiflow_block_example.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

date = None
boolean = None

oldData1 = None

date = 5
if date < 10:
  date = date + 1
if False:
  date = date + 1
else:
  date = date - 1
boolean = date <= 6
date = 0 if date <= 6 else 2
try :
  boolean = True and False
  pass
except:
  boolean = not date == 0
if date==6:
  date = date + 1
elif date==7:
  date = date + 2
else:
  date = date - 1
if date != oldData1:
  oldData1 = date
  date = date + 1
else:
  date = date - 1
  pass
```

## API
- Evaluate a condition and execute the code on the right side of "Do" if the condition is true
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Logic/uiflow_block_controls_if.svg">

```python
if date < 10:
  date = date + 1
```

<br><br>
- Evaluate a condition and execute the code on the right side of "Do" if the condition is true, otherwise execute the code on the right side of "else"
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Logic/uiflow_block_controls_ifelse.svg">

```python
if date != 10:
  date = date + 1
else:
  date = date - 1
```

<br><br>
- Boolean values can be used as substitutes for conditional expressions, where true represents a successful condition and false represents an unsuccessful one
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Logic/uiflow_block_logic_boolean.svg">

<br><br>
- Ternary operator, which can be seen as a shorthand alternative to an if-else statement
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Logic/uiflow_block_logic_ternary.svg">

```python
date = 0 if date <= 6 else 2
```

<br><br>
- Logical expressions are often used as conditions in if statements (equal to, not equal to, greater than, less than, greater than or equal to, less than or equal to) to evaluate the relationship between the data on both sides of the operation, ultimately yielding a true or false value for the if condition
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Logic/uiflow_block_logic_compare.svg">

```python
boolean = date <= 6
```

<br><br>
- Invert the logical result of an expression, i.e., notTrue becomes False, notFalse becomes True
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Logic/uiflow_block_logic_negate.svg">

```python
boolean = not date == 0
```

<br><br>
- Assigning a null value in a boolean operation context
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Logic/uiflow_block_logic_null.svg">

<br><br>
- switch-case logical syntax 
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Logic/uiflow_block_logic_switch.svg">

```python
if date==6:
  date = date + 1
elif date==7:
  date = date + 2
else:
  date = date - 1
```

<br><br>
- try-except exception handling. When code in the try block raises an exception, the program's control flow immediately jumps to the except block that matches the exception type (if any)
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Logic/uiflow_block_logic_try_except.svg">

```python
try :
  boolean = True and False
  pass
except:
  boolean = not date == 0
```

<br><br>
- and operator: The logical operation result is True if both left and right logical expressions are True, otherwise it is False
- or operator: The logical operation result is True only if both left and right logical expressions are True, otherwise it is False
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Logic/uiflow_block_logic_operation.svg">

```python
boolean = True and False
```

<br><br>
- Functions that are triggered when specific data changes
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Logic/uiflow_block_logic_when.svg">

```python
if date != oldData1:
  oldData1 = date
  date = date + 1
else:
  date = date - 1
  pass
```


