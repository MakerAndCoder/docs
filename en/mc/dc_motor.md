# [DC Motor](/en/unit/color)

## Example

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/ex.png">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
from MCLab.robocar import Robocar

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

robo = Robocar()
robo.init_motor_module()
if not robo.select_lego:
  robo.encoder4.set_all_motors_mode(0x00)
def normal_mode():
  if not robo.select_lego:
    robo.select_normal_mode()
    for i in range(4):
      robo.encoder4.set_motor_pwm_dutycycle(i, 0)

def MotorsStopAll():
  global _Direction, _For, _Type, _Speed, Distance_test, initial_ticks, required_ticks, revolutions_required
  robo.motor_stop(1)
  robo.motor_stop(2)
  robo.motor_stop(3)
  robo.motor_stop(4)

robo.set_motor_speed(1, 1, 50)
robo.set_motor_speed(2, 1, 50)
robo.set_motor_speed(3, 1, 50)
robo.set_motor_speed(4, 1, 50)
wait(2)
MotorsStopAll()
```

## API


- initialize DC motor

  
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/1">
```python
robo.init_motor_module()
```

- Move forward or backward for certain distance with specific speed
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/4">
```python
robo.init_motor_module()
```

- Stop all motors
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/3">
```python
MotorsStopAll()
```


- control motor (1~4) in direction 1 or 2 with specifc speed

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/2.png">
```python
robo.set_motor_speed(1, 1, 50)
```


- set robo turn angle

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/5.png">

```python
turn_angle(45, 0)
```


- stop motor

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/6.png">
```python
robo.motor_stop(1)
```

- run forward speed

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/7.png">

```python
robo.move_forward(50)
```

- run backward speed

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/8.png">

```python
robo.move_backward(50)
```


- run rightside speed

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/9.png">
```python
robo.move_right(50)
```


- run leftside speed


  <img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/10.png">
```python
robo.move_left(50)
```


-rotate rightside speed

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/11.png">

```python
robo.rotate_right(50)
```


rotate leftside speed

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/12.png">

```python
robo.rotate_left(50)
```


- robo angle task

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/13.png">

```python
robo.angle_task()
```

- clear encoder pulse motor

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/14.png">

```python
robo.clear_encoder_count(1)
```


- check angle task (true or false)

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/15.png">

```python
print(robo.angle_func)
```


- get encoder pulse motor (return int)
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/16.png">

```python
print(robo.get_encoder_count(1))
```


- get voltage value

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/dc_motor/17.png">

```python
print(robo.get_encoder_vin_voltage())
```

