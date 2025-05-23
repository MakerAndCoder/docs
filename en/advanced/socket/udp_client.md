
# Socket

## UDP Client

### Example

Create a UDP Client to send data to the specified server.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/socket/udp_client/uiflow_block_socket_udp_client_example.svg"> 

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import socket
import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

udpsocket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
udpsocket.connect(('192.168.31.10`', 5000))
while True:
  udpsocket.send('Hello World')
  wait(1)
  wait_ms(2)
```


### API
- Create a socket server and specify the destination IP and port to send data to.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/socket/udp_client/uiflow_block_socket_udp_client_start.svg"> 

```python
udpsocket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
udpsocket.connect(('192.168.31.10', 5000))
```
<br><br>

- Send character data
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/socket/udp_client/uiflow_block_socket_udp_client_sendmsg.svg"> 

```python
udpsocket.send('Hello World')
```
<br><br>

- Write raw data

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/socket/udp_client/uiflow_block_socket_udp_client_sendto.svg"> 

```python
udpsocket.write('')
```
<br><br>
- Send data to the specified IP and port
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/socket/udp_client/uiflow_block_socket_udp_client_sendto.svg"> 

```python
udpsocket.sendto('Hello World', ('192.168.31.10', 5000))
```
<br><br>

- Close the socket.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/socket/udp_client/uiflow_block_socket_udp_client_close.svg"> 

```python
udpsocket.close()
```
<br><br>

- Block the receiving of listening data, set the maximum buffer length, and return when data is received.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/socket/udp_client/uiflow_block_socket_udp_client_recv.svg"> 

```python
data = udpsocket.recv(1024)
```
<br><br>

- Block the receiving of listening data, and set the length of the receiving buffer, and return when the receiving buffer is full.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/socket/udp_client/uiflow_block_socket_udp_client_read.svg"> 

```python
data = udpsocket.read(10)
```



