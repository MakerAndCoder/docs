# PWM

## Example

Initialize the direction of the pin, and print the value of the pin on the screen.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/pwm/uiflow_block_pwm_demo.svg"> 

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import machine
import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

i = None

label0 = MCLabel('label0', x=90, y=55, color=0x000, font=FONT_MONT_14, parent=None)


while True:
  for i in range(13):
    PWM0.duty(i)
    wait_ms(1000)
    label0.set_text(str(i))
  wait_ms(2)

```

## API

- Set the pin, frequency, duty cycle, and timer selection for generating PWM signals.
- 
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/pwm/uiflow_block_pwm.svg"> 

```python
machine.PWM(26, freq=10000, duty=50, timer=0)
```


- Set the PWM frequency.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/pwm/uiflow_block_pwm_freq.svg"> 

```python
PWM0.freq(1)
```


- Set the PWM duty cycle.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/pwm/uiflow_block_pwm_duty.svg"> 

```python
PWM0.duty(0)
```


- Pause PWM signal generation.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/pwm/uiflow_block_pwm_pause.svg"> 

```python
PWM0.pause()
```


- Resume PWM signal generation.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/pwm/uiflow_block_pwm_resume.svg"> 

```python
PWM0.resume()
```


- Hold the PWM signal for a few microseconds.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/pwm/uiflow_block_pwm_hold_us.svg"> 

```python
PWM0.hold_us(0)
```


