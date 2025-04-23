# Module13.2 Servo2

## Example

<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/servo2/uiflow_block_servo2_example.svg">


```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import module

import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

servo2 = module.get(module.SERVO2)

while True:
  servo2.position(0, 0)
  wait_ms(100)
  servo2.position(0, 90)
  wait_ms(100)
  wait_ms(2)
```

## API
- Setting the servo rotation angle:
  - ch: 0-15
  - deg: 0-180
<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/servo2/uiflow_block_servo2_degree.svg">

```python
servo2.position(ch, deg)
```

<br><br>
- Setting the Servo Pulse Duty Cycle:
  - ch: 0-15
  - duty: 0-100
<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/servo2/uiflow_block_servo2_duty.svg">

```python
servo2.position(ch, duty=0)
```


<br><br>
- Setting the servo pulse time:
  - ch: 0-15
  - duty: 400-2500us
<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/servo2/uiflow_block_servo2_pulse.svg">

```python
servo2.position(ch, us=400)
```

<br><br>
- Release servo power:
  - ch: 0-15
<img class="blockly_svg" src="https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/static/assets/img/uiflow/blockly/modules/servo2/uiflow_block_servo2_release.svg">

```python
servo2.release(ch)
```



