# Watch Dog Timer

## Example

Set the Watch Dog Timer to reset the device when the program abnormally fails to perform the feed operation at the expected time.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/wdt/uiflow_block_wdt_example.svg"> 

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
from machine import WDT
import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

wdt = WDT(timeout=2000)
while True:
  wait(3000)
  wdt.feed()
  wait_ms(2)
```

#### API
- Initialize Watch Dog Timer and set the timeout period
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/wdt/uiflow_block_wdt_init.svg"> 

```python
wdt = WDT(timeout=2000)
```


<br><br>
- Repeat the feed operation within the timeout period to refresh, and reset the device if the timeout period is too long for the feed.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/wdt/uiflow_block_wdt_feed.svg"> 


```python
wdt.feed()
```



