# Base DMX

## Example

### Master

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dmx/uiflow_block_module_dmx_master_example.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import module

import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

dmx = module.get(module.DMX512)

dmx.dmx_init(13, 35, 12, 1)
while True:
  dmx.write_dmx_data(1, 0)
  wait(1)
  dmx.write_dmx_data(2, 0)
  wait(1)
  dmx.write_dmx_data(3, 0)
  wait(1)
  dmx.write_dmx_data(1, 255)
  wait(1)
  dmx.write_dmx_data(2, 255)
  wait(1)
  dmx.write_dmx_data(3, 255)
  wait(1)
  wait_ms(2)
```
<br><br>
### Slave

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dmx/uiflow_block_module_dmx_slave_example.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import module

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

dmx = module.get(module.DMX512)

dmx.dmx_init(13, 35, 12, 2)
while True:
  print((str('ch1:') + str((dmx.read_dmx_data(1)))))
  print((str('ch2:') + str((dmx.read_dmx_data(2)))))
  print((str('ch3:') + str((dmx.read_dmx_data(3)))))
  dmx.clear_dmx_buffer()
  wait_ms(2)
```
<br><br>
## API
- Initialize the DMX pin configuration and specify the operating mode (master/slave):
  - mode:
    - master:1
    - slave:2
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dmx/uiflow_block_module_dmx_init.svg">

```python
import module
dmx = module.get(module.DMX512)
dmx.dmx_init(tx, rx, en, mode)
```

<br><br>
- In slave mode, receive data from the specified channel.
  - ch:1-512
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dmx/uiflow_block_module_dmx_read_data.svg">

```python
dmx.read_dmx_data(ch)
```

<br><br>
- In master mode, write data to the specified channel.
  - ch:1-512
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dmx/uiflow_block_module_dmx_write_data.svg">

```python
dmx.write_dmx_data(ch, 100)
```

<br><br>
- Empty the DMX data buffer
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dmx/uiflow_block_module_dmx_clear_buffer.svg">

```python
dmx.clear_dmx_buffer()
```

<br><br>
- Inverse initialize DMX, release port resources
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/dmx/uiflow_block_module_dmx_deinit.svg">

```python
dmx.delete_port()
```



