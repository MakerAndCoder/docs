# PIN

## Example

Set the pin to output a high level for 1 second and a low level for 1 second


<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/pin/uiflow_block_pin_demo1.svg"> 

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import machine
import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

while True:
  pin0.on()
  wait(1)
  pin0.off()
  wait(1)
  wait_ms(2)
```

## API
- Set the direction of the pin.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/pin/uiflow_block_pin_pinout.svg"> 

```python
machine.Pin(0, mode=machine.Pin.IN, pull=machine.Pin.PULL_UP)
```



  
<br><br>
- Set the pin to output high level.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/pin/uiflow_block_pin_on.svg"> 

```python
pin0.on()
```
 


<br><br>
- Set the pin to output low level.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/pin/uiflow_block_pin_off.svg"> 

```python
pin0.off()
```



<br><br>
- Set the value of the pin.
  - "0": Low level
  - "1": High level
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/pin/uiflow_block_pin_set_value.svg"> 

```python
pin0.value(0)
```



<br><br>
- Get the value read from the pin.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/pin/uiflow_block_pin_get_value.svg"> 

```python
str(pin0.value())
```


