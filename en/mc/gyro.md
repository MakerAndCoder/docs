# [Gyro](/en/unit/color)

## Example

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
from MCLab.gyro_imu import Gyro
import unit

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)
servo_0 = unit.get(unit.SERVO, unit.PORTC)
color_0 = unit.get(unit.COLOR, unit.PORTA)

gyro = Gyro()

gyro.init()
while True:
  print(gyro.get_accel(0)[0])
  print(gyro.get_accel(1)[0])
  print(gyro.get_gyro(0)[0])
  print(gyro.get_gyro(1)[0])
  print(gyro.get_roll_pitch_yaw()[0])
  print(gyro.get_roll_pitch_yaw()[1])
  print(gyro.get_roll_pitch_yaw()[2])
  wait_ms(2)
```

## API

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
print(gyro.get_accel(0)[0])
```

- get accelerometer data direction (m/s2)

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
print(gyro.get_accel(1)[0])
```

- get accelerometer data direction (deg/s)


<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
print(gyro.get_gyro(0)[0])
```

- get accelerometer raw data direction

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
print(gyro.get_gyro(1)[0])
```

- get gyroscope raw data direction

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
print(gyro.get_roll_pitch_yaw()[0])
```

- set X

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
print(gyro.get_roll_pitch_yaw()[1])
```

- set Y

<img class="blockly_svg" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5b/Insert_image_here.svg/2560px-Insert_image_here.svg.png">

```python
print(gyro.get_roll_pitch_yaw()[2])
```

- set Z


