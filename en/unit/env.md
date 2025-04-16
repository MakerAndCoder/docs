# [Unit ENV/ENV-II/ENV-III/ENV-IV](/en/unit/env)

## Example

Get temperature, humidity, and atmospheric pressure data collected by ENV

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/unit/env/uiflow_block_example.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import unit

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)
env3_0 = unit.get(unit.ENV3, unit.PORTA)

while True:
  print(env3_0.pressure)
  print(env3_0.temperature)
  print(env3_0.humidity)
  wait_ms(2)
```

## API
- This method allows you to read the temperature value collected by ENV and return a floating-point value. The unit of measurement is °C.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/unit/env/uiflow_block_dht12_get_temperature.svg">

```python
print(env_0.temperature)
```

<br><br>
- This method allows you to read the relative humidity value taken by ENV and return a floating-point value. The unit of measurement is %RH.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/unit/env/uiflow_block_dht12_get_humidity.svg">

```python
print(env_0.humidity)
```

<br><br>
- This method allows you to read the atmospheres collected by ENV and return a floating-point value. The unit of measurement is Pa.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/unit/env/uiflow_block_dht12_pressure.svg">

```python
print(env_0.pressure)
```
