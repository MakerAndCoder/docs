# UART

## Example

Continuously exchange data between `uart1` and `uart2` to achieve bidirectional communication.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/uart/uiflow_block_uart_demo.svg"> 

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

uart1 = machine.UART(1, tx=1, rx=3)
uart1.init(115200, bits=8, parity=None, stop=1)
uart2 = machine.UART(2, tx=17, rx=16)
uart2.init(115200, bits=8, parity=None, stop=1)
while True:
  if uart1.any():
    uart2.write(bytes(uart1.read()))
  if uart2.any():
    uart1.write(bytes(uart2.read()))
  wait_ms(2)
```

## API

- Sets the TX and RX pins and configures the communication parameters (baud rate, data bits, parity, and stop bits) for serial communication.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/uart/uiflow_block_uart.svg"> 

```python
uart1 = machine.UART(1, tx=14, rx=13)
uart1.init(9600, bits=8, parity=None, stop=1)
```


<br> <br>  
- Sends a string via `uart1`, followed by a carriage return and newline to signify the end of the line.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/uart/uiflow_block_uart_write_line.svg"> 

```python
uart1.write('' + "\r\n")
```
 
<br> <br>
- Sends a string via `uart1`.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/uart/uiflow_block_uart_write.svg"> 

```python
uart1.write('')
```

<br> <br>
- Sends an array containing three byte values via `UART1`.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/uart/uiflow_block_uart_write_raw_data.svg"> 

```python
uart1.write(bytes([0, 0, 0]))
```

<br> <br>
- Reads the data received by `UART1` and converts it to a string.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/uart/uiflow_block_uart_read.svg"> 

```python
str(uart1.read())
```

<br> <br>
- Reads up to 10 bytes of data received by `UART1`, converts it to a string, and sets it as the text of `label0`.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/uart/uiflow_block_uart_read_characters.svg"> 

```python
label0.set_text(str(uart1.read(10)))
```
"10": Sets the maximum number of bytes.


<br> <br>
- Reads a line of data received by `UART1` and converts it to a string.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/uart/uiflow_block_uart_readline.svg"> 

```python
str(uart1.readline())
```


<br> <br>
- Checks if there is data available to read in the `UART1` receive buffer and converts the result to a string.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/uart/uiflow_block_uart_any.svg"> 

```python
str(uart1.any())
```

