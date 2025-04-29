# Module HMI

## Example

#> Print the rotary encoder count value, increment value, button status, and firmware version of the HMI Module.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/hmi/uiflow_block_hmi_demo.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import module

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

hmi = module.get(module.HMI)

hmi.init_i2c_address(0x41)
while True:
  print((str('counter value：') + str((hmi.get_counter_value()))))
  print((str('increment value：') + str((hmi.get_increment_value()))))
  print((str('button status：') + str((hmi.get_button_status(0)))))
  print((str('Firmware version：') + str((hmi.get_device_status(0xFE)))))
  wait_ms(2)
```
<br><br>
## API
- Get the status of a specified button. In the dropdown menu, there are three options to choose from. Based on the selected button, this block will return the current status of the corresponding button, such as pressed or not pressed.
  - 0: Get the status of Button 1.
  - 1: Get the status of Button 2.
  - 2: Get the status of Button 3.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/hmi/uiflow_block_module_hmi_get_button_status.svg">

```python
hmi.get_button_status(0)
```

<br><br>
- Get the current value of the counter. Returns an integer representing the cumulative count of the counter.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/hmi/uiflow_block_module_hmi_get_counter.svg">

```python
hmi.get_counter_value()
```

<br><br>
- Get the firmware version of the device. Returns a string representing the current firmware version running on the device.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/hmi/uiflow_block_module_hmi_get_device_status.svg">

```python
hmi.get_device_status(0xFE)
```

<br><br>
- Get the increment value. Returns an integer representing the incremental change of the encoder.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/hmi/uiflow_block_module_hmi_get_increment.svg">

```python
hmi.get_increment_value()
```

<br><br>
- Initialize the device's I2C address, used for communication on the I2C bus.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/hmi/uiflow_block_module_hmi_init.svg">

```python
hmi.init_i2c_address(0x41)
```

<br><br>
- Reset the counter value. This will clear the current value of the counter.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/hmi/uiflow_block_module_hmi_reset_counter.svg">

```python
hmi.reset_counter_value()
```

<br><br>
- Set the counter value. This allows you to set the counter to a specified integer value.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/hmi/uiflow_block_module_hmi_set_counter.svg">

```python
hmi.set_counter_value(1000)
```

<br><br>
- Set the I2C address of the device.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/hmi/uiflow_block_module_hmi_set_i2c_address.svg">

```python
hmi.set_i2c_address(0x41)
```

<br><br>
- Set the state of LED 1/2. You can choose to set it to ON or OFF to control the LED's state. This allows you to control the on/off status of different LEDs.
  - LED: You can choose the LED number to control, with options for 1 and 2.
  - state: You can choose the LED's state, with options for ON (on) or OFF (off).
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/hmi/uiflow_block_module_hmi_set_led.svg">

```python
hmi.set_LED(0, 1)
```

