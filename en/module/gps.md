# Module GPS

## Example

#> Serial print the device's longitude and latitude

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/gps/uiflow_block_gps_demo.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import module

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

gps = module.get(module.GPS, (14, 13))

while True:
  print((str('Latitude:') + str((gps.latitude))))
  print((str('Longitude') + str((gps.longitude))))
  wait_ms(2)
```

## API
- Get altitude in meters, returns a string
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/gps/uiflow_block_gps_get_altitude.svg">

```python
gps.altitude
```

<br><br>
- Get course information, returns a string. The course refers to the direction relative to the Earth's North Pole
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/gps/uiflow_block_gps_get_course.svg">

```python
gps.course
```

<br><br>
- Get date information, returns a string
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/gps/uiflow_block_gps_get_date.svg">

```python
gps.gps_date
```

<br><br>
- Get latitude information, returns a string. The format is degrees and minutes (ddmm.mmmmm) and includes the east/west (W/E) designation
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/gps/uiflow_block_gps_get_latitude.svg">

```python
gps.latitude
```

<br><br>
- Get latitude in decimal format, returns a float
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/gps/uiflow_block_gps_get_latitude_decimal.svg">

```python
gps.latitude_decimal
```

<br><br>
- Get longitude information, returns a string. The format is degrees and minutes (dddmm.mmmmm) and includes the north/south (S/N) designation
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/gps/uiflow_block_gps_get_longitude.svg">

```python
gps.longitude
```

<br><br>
- Get longitude in decimal format, returns a float
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/gps/uiflow_block_gps_get_longitude_decimal.svg">

```python
gps.longitude_decimal
```

<br><br>
- Get positioning quality, returns a string. Typically used to indicate the quality or accuracy of the GPS signal
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/gps/uiflow_block_gps_get_positioning_quality.svg">

```python
gps.pos_quality
```

<br><br>
- Get the number of satellites connected, returns a string
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/gps/uiflow_block_gps_get_satellite_num.svg">

```python
gps.satellite_num
```

<br><br>
- Get speed, returns a string. The speed can be in:
  - Knot: A unit of speed commonly used in maritime and aviation.
  - Kph: Kilometers per hour, commonly used in land transportation.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/gps/uiflow_block_gps_get_speed.svg">

```python
gps.speed_knot
```

<br><br>
- Get current time, returns a string
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/gps/uiflow_block_gps_get_state.svg">

```python
gps.gps_time
```

<br><br>
- Initialize with custom pins, TX pin is 17 and RX pin is 16. This is used to set custom serial communication pins
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/gps/uiflow_block_gps_set_custom.svg">

```python
module.get(module.GPS, (17, 16))
```

<br><br>
- Set the time zone, the range is -12 to 12. In this example, the time zone is set to 8
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/gps/uiflow_block_gps_set_time_zone.svg">

```python
gps.set_time_zone(8)
```

<br><br>
- Set the core UART ID number. This is used to specify the UART interface to be used
  - 1: Set the core UART ID number to 1.
  - 2: Set the core UART ID number to 2.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/gps/uiflow_block_gps_uart_init.svg">

```python
gps.uart_port_id(1)
```

