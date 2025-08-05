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

- Initializes the line sensor connected to the specified port.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/line_follower/1.svg">

```python
robo = Robocar()
robo.ow_line_port_init(unit.PORTB)
```



- Activates the built-in LED on the multi-line sensor.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/line_follower/2.svg">

```python
robo.ow_multi_line_led(1)
```


- Returns the sensor readings from a two-line sensor module.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/line_follower/3.svg">

```python
(_, _) = robo.ow_two_line_get_sensor_values()
```



- Reads the value from a specific line in a two-line sensor.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/line_follower/4.svg">

```python
robo.ow_two_line_get_sensor_value(id=1)
```



- Returns values from all sensors in a multi-line sensor module.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/line_follower/5.svg">

```python
(_, _, _, _, _) = robo.ow_multi_line_get_sensor_values()
```


- Retrieves a specific line follower channel in either digital or analog format

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/line_follower/6.svg">

```python
robo.ow_multi_line_get_sensor_value(id=1, data_type=0)
```
