# Module LoRa868

## Example

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lora868/uiflow_block_lora868_example.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import module

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

packet_size = None
check = None

lora868 = module.get(module.LORA868)

def lora868_callback(size):
  global packet_size, check
  packet_size = size
  if packet_size:
    check = lora868.read_packet()
    print(check)
  pass

def buttonA_wasPressed():
  global packet_size, check
  lora868.set_begin_packet()
  lora868.write_packet([0x48, 0x65, 0x6C, 0x6C, 0x6F])
  lora868.set_end_packet()
  pass
btnA.wasPressed(buttonA_wasPressed)

lora868.init_lora_module(cs=5, rst=13, irq=34)
lora868.set_lora_config(freq=868000000, band=125000, TxPow=17, sync=0x34, spreadfactor=7, crate=5, preamble=8, CRC=False)
lora868.set_receive_callback_handler(lora868_callback)
```

## API
- Initialize the LoRa module and specify the relevant CS, RST, IRQ pins
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lora868/uiflow_block_lora868_init.svg">

```python
import module
lora868 = module.get(module.LORA868)
lora868.init_lora_module(cs=5, rst=13, irq=34)
```

<br><br>
- Initialize LoRa configuration:
  - freq:operating frequency
  - band:
    - 7.8 kHz
    - 10.4 kHz
    - 15.6 kHz
    - 20.8kHz
    - 31.25 kHz
    - 41.7 kHz
    - 62.5 kHz
    - 125 kHz
    - 250 kHz
    - 500 kHz
  - TxPow:
    - 0-20dBm
  - sync:synchronized characters
  - spreadfactor:
    - 6-12
  - crate:C/R:
    - C/5-8
  - preamble:preamble length
  - CRC:Whether to enable CRC checking

- Please refer to [sx127x datasheet](https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/products/module/Module-LoRa433_V1.1/sx1278.pdf) for detailed configuration parameter meanings and ranges.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lora868/uiflow_block_lora868_config.svg">

```python
lora868.set_lora_config(freq=868000000, band=125000, TxPow=17, sync=0x34, spreadfactor=7, crate=5, preamble=8, CRC=False)
```

<br><br>
- Send String Data Frame
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lora868/uiflow_block_lora868_print_msg.svg">

```python
lora868.write_str_packet('')
```


<br><br>
- Initialize data frame
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lora868/uiflow_block_lora868_begin_packet.svg">

```python
lora868.set_begin_packet()
```

<br><br>
- Write data to the data frame buffer
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lora868/uiflow_block_lora868_write_buffer.svg">

```python
lora868.write_packet([0x48, 0x65, 0x6C, 0x6C, 0x6F])
```

<br><br>
- Finish editing the data frame, and execute the transmission
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lora868/uiflow_block_lora868_end_packet.svg">

```python
lora868.set_end_packet()
```


<br><br>
- Initialize the receive callback function
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lora868/uiflow_block_lora868_receive_callback.svg">

```python
lora868.set_receive_callback_handler(lora868_callback)
```


<br><br>
- Define the receive callback function, the incoming value is the size of the data frame. And through the following data reading, RSSI reading, SNR reading and other related APIs, get the data frame content in the callback.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lora868/uiflow_block_lora868_callback.svg">

```python
def lora868_callback(size):
  global packet_size
  packet_size = size
  pass
```

<br><br>
- Receives data and converts it to a string
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lora868/uiflow_block_lora868_message.svg">

```python
lora868.read_str_packet()
```


<br><br>
- Receive raw data Bytearray
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lora868/uiflow_block_lora868_read.svg">

```python
lora868.read_packet()
```


<br><br>
- Get current data frame RSSI value
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lora868/uiflow_block_lora868_packet_rssi.svg">

```python
lora868.get_rssi()
```

<br><br>
- Get the current data frame SNR value
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lora868/uiflow_block_lora868_packet_snr.svg">

```python
lora868.get_snr()
```


<br><br>
- Go to sleep mode
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lora868/uiflow_block_lora868_sleep_mode.svg">

```python
lora868.set_sleep_mode()
```

<br><br>
- Entering standby mode
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lora868/uiflow_block_lora868_stand_by_mode.svg">

```python
lora868.set_standby_mode()
```



