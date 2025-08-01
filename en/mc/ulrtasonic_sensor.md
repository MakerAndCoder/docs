# [Ultrasonic Sensor](/en/unit/color)

## Example

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import unit
from MCLab.robocar import Robocar

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

robo = Robocar()

robo.ultrasonic_port_init(unit.PORTC)
robo.ultrasonic_rgb_color(1, 0xff0000, 50)
robo.ultrasonic_rgb_color_from(1, 6, 0xff0000, 50)
```

## API

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
robo.ultrasonic_port_init(unit.PORTC)
```

- initialize ultrasonic sensor

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
robo.ultrasonic_rgb_color(1, 0xff0000, 50)
```

- set RGB ultrasonic LED index


<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
robo.ultrasonic_rgb_color_from(1, 6, 0xff0000, 50)
```

- set RGB ultrasonic LED from

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
robo.ultrasonic_rgb_color_all(0xff0000, 50)
```

- set RGB ultrasonic LED all color

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
print(robo.ultrasonic_rgb_sensor(mode=1))
```

- get RGB ultrasonic target distance value mode (return float)



