# Module13.2 PPS

## Example

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/pps/uiflow_block_pps_demo.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import module

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

pps = module.get(module.PPS)

pps.init_i2c_address(0x35)
pps.setOutput(True)
pps.setOutputVoltage(5.5)
pps.setOutputCurrent(1)
while True:
  print((str('output current:') + str((pps.readOutputCurrent()))))
  print((str('output voltage:') + str((pps.readOutputVoltage()))))
  print((str('MCU temperture:') + str((pps.readMcuTemperature()))))
  wait_ms(2)
```
<br><br>
## API
- Get the current device's I2C address
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/pps/uiflow_block_module_pps_getI2CAddress.svg">

```python
pps.getI2CAddress()
```

<br><br>
- Initialize the device's I2C address
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/pps/uiflow_block_module_pps_init.svg">

```python
pps.init_i2c_address(0x35)
```

<br><br>
- Get the data update flag, returns an integer. This flag is usually used to indicate whether the data has been updated
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/pps/uiflow_block_module_pps_readDataUpdateFlag.svg">

```python
pps.readDataUpdateFlag()
```

<br><br>
- Get the input voltage value in volts (V), returns a float. This value represents the currently measured input voltage
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/pps/uiflow_block_module_pps_readInputVoltage.svg">

```python
pps.readInputVoltage()
```

<br><br>
- Get the MCU temperature value in degrees Celsius (°C), returns a float. This value represents the currently measured microcontroller temperature
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/pps/uiflow_block_module_pps_readMcuTemperature.svg">

```python
pps.readMcuTemperature()
```

<br><br>
- Get the module ID, returns an integer. This ID is used to uniquely identify the device or module
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/pps/uiflow_block_module_pps_readModuleId.svg">

```python
pps.readModuleId()
```

<br><br>
- Get the output current value in amperes (A), returns a float. This value represents the currently measured output current
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/pps/uiflow_block_module_pps_readOutputCurrent.svg">

```python
pps.readOutputCurrent()
```

<br><br>
- Get the output voltage value in volts (V), returns a float. This value represents the currently measured output voltage
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/pps/uiflow_block_module_pps_readOutputVoltage.svg">

```python
pps.readOutputVoltage()
```

<br><br>
- Get the power module's running mode, returns an integer. This is usually used to indicate the current operating status of the power module
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/pps/uiflow_block_module_pps_readPsuRunningMode.svg">

```python
pps.readPsuRunningMode()
```

<br><br>
- Get the unique identifier (UID), returns a byte array. The UID is used to uniquely identify the device or module
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/pps/uiflow_block_module_pps_readUID.svg">

```python
pps.readUID()
```

<br><br>
- Set the device's I2C address
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/pps/uiflow_block_module_pps_setI2CAddress.svg">

```python
pps.setI2CAddress()
```

<br><br>
- Set the output state. This function is usually used to control the device's output, such as turning a feature or module on or off
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/pps/uiflow_block_module_pps_setOutput.svg">

```python
pps.setOutput(True)
```

<br><br>
- Set the output current, range is 0 to 5 amperes. This is used to control the device's output current
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/pps/uiflow_block_module_pps_setOutputCurrent.svg">

```python
pps.setOutputCurrent(1)
```

<br><br>
- Set the device's output voltage. The range is 0 to 30 volts, used to adjust the device's output voltage value, controlling power supply or voltage level
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/pps/uiflow_block_module_pps_setOutputVoltage.svg">

```python
pps.setOutputVoltage(5.5)
```

