# [Line Follower Sensor](/en/unit/color)

## Example

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/line_follower/ex.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import unit
from MCLab.robocar import Robocar


screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)


s1 = None
s2 = None
s3 = None
s4 = None
s5 = None

robo = Robocar()

label0 = MCLabel('label0', x=33, y=38, color=0x000, font=FONT_MONT_14, parent=None)
label1 = MCLabel('label1', x=33, y=73, color=0x000, font=FONT_MONT_14, parent=None)
label2 = MCLabel('label2', x=33, y=113, color=0x000, font=FONT_MONT_14, parent=None)
label3 = MCLabel('label3', x=33, y=151, color=0x000, font=FONT_MONT_14, parent=None)
label4 = MCLabel('label4', x=33, y=187, color=0x000, font=FONT_MONT_14, parent=None)




robo.ow_line_port_init(unit.PORTB)
while True:
  (s1, s2, s3, s4, s5) = robo.ow_multi_line_get_sensor_values()
  label0.set_text(str((str('1st channel:') + str(s1))))
  label1.set_text(str((str('2nd channel:') + str(s2))))
  label2.set_text(str((str('3rd channel:') + str(s3))))
  label3.set_text(str((str('4th channel:') + str(s4))))
  label4.set_text(str((str('5th channel:') + str(s5))))
  wait_ms(2)

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
