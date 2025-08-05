# Unit Servo

## Example

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/units/servo/ex.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import time
import unit


screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)
servo_0 = unit.get(unit.SERVO, unit.PORTC)

while True:
  servo_0.write_angle(0)
  wait(2)
  servo_0.write_angle(50)
  wait_ms(2)```

## API

- Rotates the servo motor to the given angle (0–180°).

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/units/servo/1.svg">

```python
servo_0.write_angle(0)
```

- Controls the servo position by setting the pulse width in microseconds (typically 500–2500 µs).
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/units/servo/2.svg">

```python
servo_0.write_us(600)
```
