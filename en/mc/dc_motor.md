# [DC Motor](/en/unit/color)

## Example

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/ex.png">

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

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

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



```

- initialize DC motor

  
<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">


- Stop all motors

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/3.svg/2560px-Insert_image_here.svg.png">

```python
MotorsStopAll(
```


- control motor (1~4) in direction 1/2 with specifc speed

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/4.png">
```python
robo.set_motor_speed(1, 1, 50)
```

- set robo turn angle

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/5.png">

```python
turn_angle(45, 0)
```


- stop motor

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/6.png">
```python
robo.motor_stop(1)
```

- run forward speed

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/7.png">

```python
robo.move_forward(50)
```

- run backward speed

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/8.png">

```python
robo.move_backward(50)
```


- run rightside speed

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/9.png">
```python
robo.move_right(50)
```


- run leftside speed


  <img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/10.png">
```python
robo.move_left(50)
```


-rotate rightside speed

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/11.png">

```python
robo.rotate_right(50)
```


rotate leftside speed

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/12.png">

```python
robo.rotate_left(50)
```


- robo angle task

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/13.png">

```python
robo.angle_task()
```

- clear encoder pulse motor

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/14.png">

```python
robo.clear_encoder_count(1)
```


- check angle task (true or false)

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/15.png">

```python
print(robo.angle_func)
```


- get encoder pulse motor (return int)
<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/16.png">

```python
print(robo.get_encoder_count(1))
```


- get voltage value

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/17.png">

```python
print(robo.get_encoder_vin_voltage())
```

