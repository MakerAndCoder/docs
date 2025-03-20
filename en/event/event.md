# Event

## Loop

### Example

- Loop print Hello MC4.0

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_loop_example.svg"> 


```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

while True:
  print('Hello MC4.0')
  wait_ms(2)
```


### API

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_loop.svg"> 

```python
while True:
  wait_ms(2)
```

- Infinite loop execution of the program contained in the Loop

## Button

### Example

- Getting the state of a key by callback or polling

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_button_example1.svg">

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_button_example2.svg">

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_button_example3.svg">


```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)


def multiBtnCb_AB():
  # global params
  print('Button A + B Pressed')
  pass
btn.multiBtnCb(btnA,btnB,multiBtnCb_AB)

def buttonA_wasPressed():
  # global params
  print('Button A Pressed')
  pass
btnA.wasPressed(buttonA_wasPressed)


while True:
  if btnB.wasPressed():
    print('Button B was Press')
  elif btnC.pressFor(0.8):
    print('Button C Long Press')
  wait_ms(2)
```

### API


<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_button_init.svg"> 

```python
btn = btn.attach([pin])
```

- Initialize the keys and specify the input pins.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_button_callback.svg">

```python
def buttonA_wasPressed():
  # global params
  # your code here
  pass
btnA.wasPressed(buttonA_wasPressed)
```

- Bind key event callback function, optional event.
  - wasPressed
  - wasReleased
  - LongPress
  - wasDoublePress

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_button_callback_multi.svg"> 

```python
def multiBtnCb_AB():
  # global params
  # your code here
  pass
btn.multiBtnCb(btnA,btnB,multiBtnCb_AB)
```
- Bind multi-key event callback function, only support two-key combination, triggered when pressing keys at the same time.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_button_read.svg"> 

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_button_read_status.svg"> 

```python
if btnA.wasPressed():
  print('Button A wasPressed')
if btnA.pressFor(0.8):
  print('Button A Pressed')
```

- Read current key state, return True/False according to event configuration, optional events.
  - wasPressed
  - wasReleased
  - LongPress
  - wasDoublePress


## Software Timer

### Example

- Configure the software timer to print in 100ms cycles.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_software_timer_example.svg"> 


```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)


@timerSch.event('timer1')
def ttimer1():
  # global params
  print('This is a software timer!')
  pass


timerSch.setTimer('timer1', 100, 0x00)
timerSch.run('timer1', 100, 0x00)
```

### API

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_software_timer_callback.svg"> 

```python
@timerSch.event('timer1')
def ttimer1():
  # global params
  pass
```

- Setting the Software Timer Callback Function

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_software_timer_set.svg"> 

```python
timerSch.setTimer('timer1', 100, 0x00)
```

- Sets the software timer period. the timer mode supports the following configurations:
  - PERIODIC 0x00: Cycle execution
  - ONE_SHOT 0x01: Single execution

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_software_timer_start.svg"> 

```python
timerSch.run('timer1', 100, 0x00)
```

- Enable the software timer to configure the period at the same time. the timer mode supports the following configurations:
  - PERIODIC 0x00: Cycle execution
  - ONE_SHOT 0x01: Single execution


<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_software_timer_stop.svg"> 

```python
timerSch.stop('timer1')
```

- Stopping the software timer

## Hardware Timer

### Example

- Configure the hardware timer to print in 100ms cycles.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_hardware_timer_example.svg"> 


```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

def callback_timer3(_arg):
  # global params
  print('This is a software timer!')
  pass


timerSch.timer.init(period=100, mode=timerSch.timer.PERIODIC, callback=callback_timer3)
```

### API

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_hardware_timer_set.svg">

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/event/uiflow_block_hardware_timer_callback.svg"> 


```python
def callback_timer3(_arg):
  pass

timerSch.timer.init(period=100, mode=timerSch.timer.PERIODIC, callback=callback_timer3)
```

- Configure the timer period, timer mode, and callback function. The timer mode supports the following configurations:
  - PERIODIC: Cycle execution
  - ONE_SHOT: Single execution


