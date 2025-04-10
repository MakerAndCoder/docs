# CAN

## Example

Use ESP32 internal CAN controller resources to realize CAN bus data sending and receiving, Note: Before using, you need to access [CAN UNIT](https://shop.m5stack.com/products/canbus-unitca-is3050g) for the device.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/can/uiflow_block_can_example.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
from machine import CAN
import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

frame = None

label1 = MCLabel('label0', x=35, y=16, color=0x000, font=FONT_MONT_14, parent=None)
label3 = MCLabel('label0', x=71, y=53, color=0x000, font=FONT_MONT_14, parent=None)
label4 = MCLabel('label2', x=113, y=113, color=0x000, font=FONT_MONT_14, parent=None)
label5 = MCLabel('label3', x=138, y=156, color=0x000, font=FONT_MONT_14, parent=None)

def buttonA_wasPressed():
  global frame
  can.send([0, 1, 2, 3, 4, 5, 6, 7], 0)
  pass
btnA.wasPressed(buttonA_wasPressed)

def buttonB_wasPressed():
  global frame
  can.clear_tx_queue()
  can.clear_rx_queue()
  pass
btnB.wasPressed(buttonB_wasPressed)

def buttonC_wasPressed():
  global frame
  can.restart()
  pass
btnC.wasPressed(buttonC_wasPressed)

can = CAN(0, extframe=True, mode=CAN.NORMAL, baudrate=CAN.BAUDRATE_25K, tx_io=17, rx_io=16, auto_restart=False)
while True:
  label1.set_text(str(can.state()))
  if can.any():
    frame = can.recv()
    label3.set_text(str(frame[0]))
    label4.set_text(str(frame[1]))
    label5.set_text(str(frame[3]))
  wait_ms(30)
  wait_ms(2)
```

## API

- Initialize CAN bus, configure frame expansion mode, operating mode (normal mode, loopback mode, etc.) and baud rate setting.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/can/uiflow_block_can_init.svg">

```python
from machine import CAN
can = CAN(0, extframe=True, mode=CAN.NORMAL, baudrate=CAN.BAUDRATE_25K, tx_io=17, rx_io=16, auto_restart=False)
```

<br><br>
- Check for unread data in FIFOs
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/can/uiflow_block_can_any.svg">

```python
can.any()
```


<br><br>
- receive data
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/can/uiflow_block_can_recv.svg">

```python
frame = can.recv()
```


<br><br>
- Sends a piece of data and specifies the ID of the data frame, the ID length is 1 byte, the incoming data type is required to be `list` or `tuple`, and the data length of the data frame is required to be `8 bytes`.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/can/uiflow_block_can_send.svg">

```python
can.send([0, 1, 2, 3, 4, 5, 6, 7], id)
```

<br><br>
- Setting up filter groups
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/can/uiflow_block_can_set_filter.svg">

```python
can.setfilter(0, CAN.FILTER_RAW_SINGLE, [])
```

<br><br>
- Get CAN controller status
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/can/uiflow_block_can_state.svg">

```python
can.state()
```


<br><br>
- Clear the receive queue
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/can/uiflow_block_can_clear_rx_queue.svg">

```python
can.clear_rx_queue()
```

<br><br>
- Clearing the send queue
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/can/uiflow_block_can_clear_tx_queue.svg">

```python
can.clear_tx_queue()
```


<br><br>
- Clear Filter Groups

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/can/uiflow_block_can_clearfilter.svg">

```python
can.clearfilter()
```

<br><br>
- Reboot CAN bus
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/can/uiflow_block_can_restart.svg">

```python
can.restart()
```

<br><br>
- Stop CAN bus
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/can/uiflow_block_can_deinit.svg">

```python
can.deinit()
```



