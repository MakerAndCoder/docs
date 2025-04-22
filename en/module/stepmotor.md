# Module Stepmotor

## Example

#> Move the stepper motor back and forth at a set speed in the X, Y, and Z directions, waiting for 2 seconds after each move.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/stepmotor/uiflow_block_stepmotor_demo.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import module
import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

stepmotor1 = module.get(module.STEP_MOTOR, 0x70)
stepmotor1.set_mode("distance")
while True:
  stepmotor1.turn(x=(-10),  y=(-10), z=(-10), speed=300)
  wait(2)
  stepmotor1.turn(x=10,  y=10, z=10, speed=300)
  wait(2)
  wait_ms(2)
```

## API
- Sends a G-code command to the stepper motor controller. This is typically used to control the stepper motor to execute complex paths or operations.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/stepmotor/uiflow_block_motor_g_code.svg">

```python
stepmotor1.g_code('')
```

<br><br>
- Initializes the stepper motor and sets its I2C address to 0x70. This is the address used for communication between the stepper motor and the controller.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/stepmotor/uiflow_block_motor_instance.svg">

```python
module.get(module.STEP_MOTOR, 0x70)
```

<br><br>
- Locks the stepper motor, preventing it from moving when not unlocked. This is typically used to ensure the motor is in a stable state before executing operations.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/stepmotor/uiflow_block_motor_lock.svg">

```python
stepmotor1.lock_motor()
```

<br><br>
- Controls the stepper motor to move in the X, Y, and Z directions, with speed determined by the Speed parameter. This block allows precise control of the stepper motor's movement.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/stepmotor/uiflow_block_motor_move_xyz.svg">

```python
stepmotor1.turn(x=0,  y=0, z=0, speed=0)
```

<br><br>
- Sets the stepper motor mode to "distance" mode. This means the motor's movement will be based on the specified distance rather than other modes (such as speed mode).
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/stepmotor/uiflow_block_motor_set_mode.svg">

```python
stepmotor1.set_mode("distance")
```

<br><br>
- Unlocks the stepper motor, allowing it to move freely. This block is typically used to unlock the motor after the operation is completed.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/stepmotor/uiflow_block_motor_unlock.svg">

```python
stepmotor1.unlock_motor()
```

