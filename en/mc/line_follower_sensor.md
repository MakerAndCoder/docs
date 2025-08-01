# [Line Follower Sensor](/en/unit/color)

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



robo.ow_line_port_init(unit.PORTB)
robo.ow_multi_line_led(1)
(1, 1, 1, 1, 1) = robo.ow_multi_line_get_sensor_values()
```

## API

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
robo.ow_line_port_init(unit.PORTB)
```

- initialize line follower sensor

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
robo.ow_multi_line_led(1)
```

- set multiline line follower sensor LED


<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
(1, 1, 1, 1, 1) = robo.ow_multi_line_get_sensor_values()
```

- get multi channel line follower sensor

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
(_, _) = robo.ow_two_line_get_sensor_values()
```

- get two channel line follower sensor

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
print(robo.ow_two_line_get_sensor_value(id=1))
```

- get two channel line follower sensor (convert to int)

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
print(robo.ow_multi_line_get_sensor_value(id=1, data_type=0))
```

-get multi channel line follower sensor (convert to int)
