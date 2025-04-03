# Repeat

## Example

Loop function usage

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/loops/uiflow_block_example.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

date = None
list2 = None
i = None
j = None

date = 10
list2 = [5, 6, 7]
for count in range(10):
  date = date + 1
while date < 25:
  date = date * 2
for i in list2:
  date = date + i
  for j in range(0, 6, 2):
    date = date + 1
  if j == 3:
    break
```

## API
- Customize the number of times to run the content of the do block
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/loops/uiflow_block_controls_repeat.svg">

```python
for count in range(10):
  date = date + 1
```

<br><br>
- Iterate through the contents of an array sequentially, assigning each value to the variable i, and executing the content of the do block once for each iteration
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/loops/uiflow_block_controls_forEach.svg">

```python
list2 = [5, 6, 7]
for i in list2:
  date = date + i
```
<br><br>
- Perform a series of operations in a loop until a condition is no longer satisfied
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/loops/uiflow_block_controls_whileUntil.svg">

```python
while date < 25:
  date = date * 2
```

<br><br>
- Increment from a to b, with each increment being c, and assign each incremented result to the variable i. For each iteration, execute the content of the do block once
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/loops/uiflow_block_controls_for.svg">

```python
for j in range(0, 6, 2):
  date = date + 1
  if j == 3:
    break
```


<br><br>
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/loops/uiflow_block_controls_flow_statements.svg">

```python
break
```

