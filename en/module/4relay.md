# Module13.2 4Relay

## Example


#> Close and disconnect the relay one second apart


<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/4relay/uiflow_block_4relay_demo1.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import module

import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

relay4 = module.get(module.RELAY4)

relay4_0 = relay4.init_i2c_address(0x26)
while True:
  relay4_0.set_all_relay_state(1)
  wait(1)
  relay4_0.set_all_relay_state(0)
  wait(1)
  wait_ms(2)
```
<br><br>
## API
- Retrieves the 12-bit ADC raw value, returning an integer ranging from 0 to 4095. This is the unprocessed voltage data read from the specified module's ADC.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/4relay/uiflow_block_module_relay4_get_12bit_raw_value.svg">

```python
relay4_0.get_adc_12bit_value(0)
```

<br><br>
- Retrieves the voltage value from the 12-bit ADC, returning a voltage value ranging from 0 to 26 volts.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/4relay/uiflow_block_module_relay4_get_12bit_voltage_value.svg">

```python
relay4_0.get_adc_12bit_value(1)
```

<br><br>
- Retrieves the 8-bit ADC raw value, returning an integer ranging from 0 to 255. This is the unprocessed voltage data read from the specified module's ADC.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/4relay/uiflow_block_module_relay4_get_8bit_raw_value.svg">

```python
relay4_0.get_adc_8bit_value(0)
```

<br><br>
- Retrieves the voltage value from the 8-bit ADC, returning a voltage value ranging from 0 to 26 volts.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/4relay/uiflow_block_module_relay4_get_8bit_voltage_value.svg">

```python
relay4_0.get_adc_8bit_value(1)
```

<br><br>
- Retrieves the status of the relay module, returning a value of 0 or 1.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/4relay/uiflow_block_module_relay4_get_status.svg">

```python
relay4_0.get_relay_status(1)
```

<br><br>
- Initializes the I2C address of the device.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/4relay/uiflow_block_module_relay4_init_i2c_address.svg">

```python
relay4.init_i2c_address(0x26)
```

<br><br>
- Sets the state of all relays.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/4relay/uiflow_block_module_relay4_set_all_relay_state.svg">

```python
relay4_0.set_all_relay_state(1)
```

<br><br>
- Sets the I2C slave address of the device.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/4relay/uiflow_block_module_relay4_set_i2c_address.svg">

```python
relay4_0.set_i2c_address(0x26)
```

<br><br>
- Sets the state of relay 1.
  - Parameter 1: Relay number (1-4)
  - Parameter 2: "ON" to close the relay, "OFF" to open the relay.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/4relay/uiflow_block_module_relay4_set_state.svg">

```python
relay4_0.set_relay_state(1, 1)
```

