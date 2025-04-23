# Module13.2 GRBL

## Example


<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/grbl/uiflow_block_grbl_example.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import module

import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

grbl = module.get(module.GRBL)

grbl.set_mode("distance")
while True:
  grbl.turn(10, 10, 10, 100)
  wait(5)
  grbl.turn((-10), (-10), (-10), 100)
  wait(5)
  wait_ms(2)
```

## API
- Setting the GRBL operating mode:
  - distance:Distance control mode
  - absolute:Absolute position control mode
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/grbl/uiflow_block_grbl_set_mode.svg">

```python
grbl.set_mode("distance")
```

<br><br>
- In distance control mode, the stepper motor is controlled to move a specified distance.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/grbl/uiflow_block_grbl_turn.svg">

```python
grbl.turn(10, 10, 10, speed)
```

<br><br>
- Send GRBL G-code for control.
  - See [GRBL - Github](https://github.com/grbl/grbl/wiki) for the contents of the directive
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/grbl/uiflow_block_grbl_g_code.svg">

```python
grbl.g_code('')
```

<br><br>
- Blocking waiting for the motor to stop running
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/grbl/uiflow_block_grbl_wait_idle.svg">

```python
grbl.wait_idle()
```


<br><br>
- Determines whether the motor is in a locked state.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/grbl/uiflow_block_grbl_in_lock.svg">

```python
grbl.in_lock()
```

<br><br>
- Locking at the end of motor operation
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/grbl/uiflow_block_grbl_lock_motor.svg">

```python
grbl.lock_motor()
```

<br><br>
- Determine whether the motor is idle or not
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/grbl/uiflow_block_grbl_read_idle.svg">

```python
grbl.read_idle()
```

<br><br>
- Read GRBL control return information
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/grbl/uiflow_block_grbl_read_line.svg">

```python
grbl.read_line()
```

<br><br>
- Unlock motor lock state after limit trigger
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/grbl/uiflow_block_grbl_unlock.svg">

```python
grbl.unlock()
```

<br><br>
- No locking after the motor has finished running
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/grbl/uiflow_block_grbl_unlock_motor.svg">

```python
grbl.unlock_motor()
```

<br><br>
- Clear GRBL return data message

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/grbl/uiflow_block_grbl_read_clean.svg">

```python
grbl.read_clean()
```


