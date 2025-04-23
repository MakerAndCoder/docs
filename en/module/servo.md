# Module Servo

## Example

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/servo/uiflow_block_servo_example.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import module

import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

i = None

servo = module.get(module.SERVO)

import random

while True:
  i = random.randint(0, 180)
  servo.write_angle(0, i)
  servo.write_angle(1, i)
  servo.write_angle(2, i)
  servo.write_angle(3, i)
  servo.write_angle(4, i)
  print((str("Servo's Status") + str(i)))
  wait(0.5)
  wait_ms(2)
```

## API
- Drive Servo Rotation Angle
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/servo/uiflow_block_servo_angle.svg">

```python
servo.write_angle(0, 180)
```

<br><br>
- Drive servo pulse duration
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/servo/uiflow_block_servo_write.svg">

```python
servo.write_us(0, 600)
```



