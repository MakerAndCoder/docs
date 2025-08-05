# [Ultrasonic Sensor](/en/unit/color)

## Example

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ultrasonic/ex.svg">

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

label0 = MCLabel('label0', x=42, y=93, color=0x000, font=FONT_MONT_14, parent=None)
label1 = MCLabel('label1', x=47, y=146, color=0x000, font=FONT_MONT_14, parent=None)


robo.ultrasonic_port_init(unit.PORTC)
robo.ultrasonic_rgb_color_all(0xff0000, 50)
while True:
  label0.set_text(str((str('Distance (mm):') + str((robo.ultrasonic_rgb_sensor(mode=1))))))
  label1.set_text(str((str('Distance (cm):') + str((robo.ultrasonic_rgb_sensor(mode=2))))))
  wait_ms(2)
```

## API
- Set up the ultrasonic sensor by assigning it to PORTC.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ultrasonic/1.svg">

```python
robo = Robocar()
robo.ultrasonic_port_init(unit.PORTC)
```

- Set the color and brightness of the first LED on the ultrasonic sensor.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ultrasonic/2.svg">

```python
robo.ultrasonic_rgb_color(1, 0xff0000, 50)
```

- Set the color and brightness from LED 1 to LED 6 on the ultrasonic sensor.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ultrasonic/3.svg">

```python
robo.ultrasonic_rgb_color_from(1, 6, 0xff0000, 50)
```


- Apply a single color and brightness setting to all LEDs on the ultrasonic sensor.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ultrasonic/4.svg">

```python
robo.ultrasonic_rgb_color_all(0xff0000, 50)
```


- Retrieves the measured distance in either mm or cm.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/ultrasonic/5.svg">

```python
robo.ultrasonic_rgb_sensor(mode=1)
```
