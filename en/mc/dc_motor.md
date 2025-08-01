# [DC Motor](/en/unit/color)
## Example

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
from MCLab.robocar import Robocar
import unit

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)
motor_0 = unit.get(unit.DCMOTOR, unit.PORTA)

robo = Robocar()
robo.init_motor_module()
if not robo.select_lego:
  robo.encoder4.set_all_motors_mode(0x00)

robo.set_motor_speed(1, 1, 50)
robo.set_motor_speed(2, 1, 50)
robo.set_motor_speed(3, 1, 50)
robo.set_motor_speed(4, 1, 50)
robo.motor_stop_all()
```

## API

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
robo.move_distance(distance=5, speed=50)
```

- Move [distance] cm at [speed] %

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
robo.motor_stop_all()
```

- Motor stop all

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
robo.set_motor_speed(motor_id=1, direction=1, speed=50)
```

- Set motor control motor [motor_id] dir [direction] speed [speed]

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
robo.turn_angle(angle=90, direction="left")
```

- Set robo turn angle [angle] dir [direction]

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
robo.step_motor(motor_id=1)
```

- Motor step motor [motor_id]

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
robo.run_forward(speed=50)
```

- Run forward speed [speed] %

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
robo.run_backward(speed=50)
```

- Run backward speed [speed] %

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
robo.turn_left(speed=50)
```

- Turn left speed [speed] %

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
robo.turn_right(speed=50)
```

- Turn right speed [speed] %

Let me know when you'd like to add the next module!
