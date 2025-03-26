# IMU

##  Example

Reads and displays current IMU attitude data.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/imu/uiflow_block_imu_example.svg"> 


```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import imu

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

imu0 = imu.IMU()

while True:
  print((str('X:') + str((imu0.ypr[1]))))
  print((str('Y:') + str((imu0.ypr[2]))))
  print((str('X ACC:') + str((imu0.acceleration[0]))))
  print((str('Y ACC:') + str((imu0.acceleration[1]))))
  print((str('Z ACC:') + str((imu0.acceleration[2]))))
  print((str('X Gyr:') + str((imu0.gyro[0]))))
  print((str('Y Gyr:') + str((imu0.gyro[1]))))
  print((str('Z Gyr:') + str((imu0.gyro[2]))))
  wait_ms(2)
```


## API
- Getting the roll-over data
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/imu/uiflow_block_imu_get_x.svg"> 

```python
imu0.ypr[1]
```



<br><br>
- Getting pitch data
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/imu/uiflow_block_imu_get_y.svg"> 

```python
imu0.ypr[2]
```


<br><br>
- Getting X-axis acceleration data
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/imu/uiflow_block_imu_get_x_acc.svg"> 

```python
imu0.acceleration[0]
```


<br><br>
- Get Y-axis acceleration data
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/imu/uiflow_block_imu_get_y_acc.svg"> 

```python
imu0.acceleration[1]
```


<br><br>
- Getting Z-axis acceleration data
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/imu/uiflow_block_imu_get_z_acc.svg"> 

```python
imu0.acceleration[2]
```


<br><br>
- Get angular velocity in X direction
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/imu/uiflow_block_imu_get_x_gyr.svg"> 

```python
imu0.gyro[0]
```



<br><br>
- Get the angular velocity in the Y direction
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/imu/uiflow_block_imu_get_y_gyr.svg"> 

```python
imu0.gyro[1]
```



<br><br>
- Get angular velocity in Z direction
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/imu/uiflow_block_imu_get_z_gyr.svg"> 

```python
imu0.gyro[2]
```


