# [Gyroscope](/en/unit/color)

## Example

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/gyro/ex.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
from MCLab.gyro_imu import Gyro
import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

gyro = Gyro()

label0 = MCLabel('label0', x=39, y=67, color=0x000, font=FONT_MONT_14, parent=None)
label1 = MCLabel('label1', x=39, y=111, color=0x000, font=FONT_MONT_14, parent=None)
label2 = MCLabel('label2', x=39, y=158, color=0x000, font=FONT_MONT_14, parent=None)


gyro.init()
while True:
  label0.set_text(str((str('Accelerometer (X):') + str((gyro.get_accel(0)[0])))))
  label1.set_text(str((str('Accelerometer (Y):') + str((gyro.get_accel(0)[1])))))
  label2.set_text(str((str('Accelerometer (Z):') + str((gyro.get_accel(0)[2])))))
  wait(1)
  wait_ms(2)
```

## API

---

Initialize the Gyroscope Sensor

- Set up and initialize the gyroscope sensor before collecting data.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/gyro/1.svg">

```python
gyro = Gyro()
gyro.init()
```



Get X-axis Acceleration (m/s²) from Accelerometer 0

- Reads acceleration value along X-axis from accelerometer 0.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/gyro/2.svg">

```python
gyro.get_accel(0)[0]
```



Get X-axis Acceleration (m/s²) from Accelerometer 1

- Reads acceleration value along X-axis from accelerometer 1.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/gyro/3.svg">

```python
gyro.get_accel(1)[0]
```



Get X-axis Rotation Speed (°/s) from Gyroscope 0

- Reads angular velocity around X-axis from gyroscope 0.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/gyro/4.svg">

```python
gyro.get_gyro(0)[0]
```



Get X-axis Rotation Speed (°/s) from Gyroscope 1

- Reads angular velocity around X-axis from gyroscope 1.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/gyro/5.svg">

```python
gyro.get_gyro(1)[0]
```



Get Roll Angle (°) from Orientation Data

- Retrieves the roll angle representing tilt side to side.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/gyro/6.svg">

```python
gyro.get_roll_pitch_yaw()[0]
```



Get Pitch Angle (°) from Orientation Data

- Retrieves the pitch angle representing tilt forward and backward.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/gyro/7.svg">

```python
gyro.get_roll_pitch_yaw()[1]
```


Get Yaw Angle (°) from Orientation Data

- Retrieves the yaw angle representing rotation around the vertical axis.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/gyro/8.svg">

```python
gyro.get_roll_pitch_yaw()[2]
```
