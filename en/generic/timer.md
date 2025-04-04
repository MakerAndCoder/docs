# Timer

## Example

Program delay and print runtime

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/timer/uiflow_block_timer_wait_example.svg"> 

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

print(time.ticks_ms())
wait_ms(100)
print(time.ticks_ms())
wait(1)
print(time.ticks_ms())
```

## API
<br><br>
- Program delay/ms
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/timer/uiflow_block_timer_wait_ms.svg"> 

```python
wait_ms(100)
```


<br><br>
- Program delay/s
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/timer/uiflow_block_timer_wait_sec.svg"> 

```python
wait(1)
```


<br><br>
- Get current runtime/ms
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/timer/uiflow_block_timer_get_ticks_ms.svg"> 

```python
print(time.ticks_ms())
```



