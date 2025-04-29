# Module13.2 Dual Kmeter

## Example
#> Loop to print the device firmware version, selected channel, thermocouple temperature (in Celsius and Fahrenheit), and internal temperature (in Celsius and Fahrenheit), with a 250-millisecond delay between each loop.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dual_kmeter/uiflow_block_dual_kmeter_demo.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import module

import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

dualkmeter = module.get(module.DUAL_KMETER)

dualkmeter.init_i2c_address(0x11)
print((str('Firmware：') + str((dualkmeter.get_firmware_version()))))
while True:
  if dualkmeter.get_isready():
    print((str('Kmeter channel:') + str((dualkmeter.rw_select_kmeter()))))
    print((str('Thermocouple temperature(CELSIUS):') + str((dualkmeter.get_kmeter_thermo(1)))))
    print((str('Internal temperature(CELSIUS):') + str((dualkmeter.get_kmeter_internal(1)))))
    print((str('Thermocouple temperature(FAHRENHEIT):') + str((dualkmeter.get_kmeter_thermo(2)))))
    print((str('Internal temperature(FAHRENHEIT):') + str((dualkmeter.get_kmeter_internal(2)))))
  wait_ms(250)
  wait_ms(2)
```

## API
- Get the selected channel. Returns the currently selected channel.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dual_kmeter/uiflow_block_module_dualkmeter_get_channel.svg">

```python
dualkmeter.rw_select_kmeter()
```

<br><br>
- Get the device's firmware version. Returns a string representing the firmware version currently running on the device.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dual_kmeter/uiflow_block_module_dualkmeter_get_fw_version.svg">

```python
dualkmeter.get_firmware_version()
```

<br><br>
- Get the internal temperature. You can choose the unit as Celsius (CELSIUS) or Fahrenheit (FAHRENHEIT), and it returns a float representing the temperature.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dual_kmeter/uiflow_block_module_dualkmeter_get_internal_temp.svg">

```python
dualkmeter.get_kmeter_internal(1)
```

<br><br>
- Check if the temperature measurement is ready. Returns a boolean value indicating whether the temperature measurement can be performed.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dual_kmeter/uiflow_block_module_dualkmeter_get_isready.svg">

```python
dualkmeter.get_isready()
```

<br><br>
- Get the internal temperature as a string. You can choose the unit as Celsius (CELSIUS) or Fahrenheit (FAHRENHEIT), and it returns a string representing the temperature.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dual_kmeter/uiflow_block_module_dualkmeter_get_str_internal_temp.svg">

```python
dualkmeter.get_kmeter_internal_string(1)
```

<br><br>
- Get the thermocouple temperature as a string. You can choose the unit as Celsius (CELSIUS) or Fahrenheit (FAHRENHEIT), and it returns a string representing the temperature.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dual_kmeter/uiflow_block_module_dualkmeter_get_str_thermo_temp.svg">

```python
dualkmeter.get_kmeter_thermo_string(1)
```

<br><br>
- Get the thermocouple temperature. You can choose the unit as Celsius (CELSIUS) or Fahrenheit (FAHRENHEIT), and it returns a float representing the temperature.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dual_kmeter/uiflow_block_module_dualkmeter_get_thermo_temp.svg">

```python
dualkmeter.get_kmeter_thermo(1)
```

<br><br>
- Initialize the device's I2C address.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dual_kmeter/uiflow_block_module_dualkmeter_init_i2c.svg">

```python
dualkmeter.init_i2c_address(0x11)
```

<br><br>
- Set one of the two thermocouples as the measurement channel.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dual_kmeter/uiflow_block_module_dualkmeter_set_channel.svg">

```python
dualkmeter.rw_select_kmeter(0)
```

<br><br>
- Set one of the two thermocouples as the measurement channel.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dual_kmeter/uiflow_block_module_dualkmeter_set_channel2.svg">

```python
dualkmeter.rw_select_kmeter(0)
```

