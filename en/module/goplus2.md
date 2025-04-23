# Module13.2 GoPlus2

## Example

#> Toggle the angle values of 4 servos every second, and change the speed and direction of rotation of the motors.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/goplus2/uiflow_block_go_plus2_demo.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import module

import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

go_plus_2 = module.get(module.GOPLUS2)

while True:
  go_plus_2.set_servo_angle(go_plus_2.S1, 180)
  go_plus_2.set_servo_angle(go_plus_2.S2, 0)
  go_plus_2.set_servo_angle(go_plus_2.S3, 90)
  go_plus_2.set_servo_angle(go_plus_2.S4, 45)
  go_plus_2.set_motor_speed(go_plus_2.MB, 0)
  go_plus_2.set_motor_speed(go_plus_2.MA, 127)
  wait(1)
  go_plus_2.set_servo_plus(go_plus_2.S1, 800)
  go_plus_2.set_servo_plus(go_plus_2.S2, 1500)
  go_plus_2.set_servo_plus(go_plus_2.S3, 500)
  go_plus_2.set_servo_plus(go_plus_2.S4, 2500)
  go_plus_2.set_motor_speed(go_plus_2.MA, 0)
  go_plus_2.set_motor_speed(go_plus_2.MB, (-127))
  wait(1)
  wait_ms(2)
```

## API
- Read the analog value of the pin. Returns an analog value representing the voltage.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/goplus2/uiflow_block_go_plus2_analog_read.svg">

```python
go_plus_2.analog_read(go_plus_2.PB1)
```

<br><br>
- Read the digital value of the pin. Returns a digital value representing the high or low state.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/goplus2/uiflow_block_go_plus2_digital_read.svg">

```python
go_plus_2.digital_read(go_plus_2.PB1)
```

<br><br>
- Set the pin to digital output 0 (low level).
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/goplus2/uiflow_block_go_plus2_digital_write.svg">

```python
go_plus_2.digital_write(go_plus_2.PB1, 0)
```

<br><br>
- Set the motor speed. The speed value can be positive or negative, used to control the motor's speed and direction.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/goplus2/uiflow_block_go_plus2_set_motor_speed.svg">

```python
 go_plus_2.set_motor_speed(go_plus_2.MA, 0)
```

<br><br>
- Set the angle of servo S1 to 0. The angle value can be within the servo's range and is used to control the servo's position.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/goplus2/uiflow_block_go_plus2_set_servo_angle.svg">

```python
go_plus_2.set_servo_angle(go_plus_2.S1, 0)
```

<br><br>
- Adjust the position of the servo by increasing the specified increment value (PWM).
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/goplus2/uiflow_block_go_plus2_set_servo_plus.svg">

```python
 go_plus_2.set_servo_plus(go_plus_2.S1, 500)
```

