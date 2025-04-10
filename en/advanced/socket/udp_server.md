
# Socket

## UDP Server

### Example

Create a UDP Server to listen for data reception, and send back the same data content. Through the network-related APIs can get the current IP address of the local machine, used to provide other Client data sending.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/socket/uiflow_block_socket_udp_server_example.svg"> 


```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import network
import wifiCfg
import time
import socket

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

wlan = network.WLAN(network.STA_IF)
wlan.active(True)
wifiCfg.doConnect('', '')
while not (wifiCfg.wlan_sta.isconnected()):
  print('Wi-Fi connecting...')
  wait(1)
print(wlan.ifconfig())

udpsocket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
udpsocket.bind(('0.0.0.0', 5000))
while True:
  print(udpsocket.recv(1024))
  wait_ms(2)
```


### API
- Create a socket server and specify the IP (usually 0.0.0.0 is used to listen locally) and the port.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/socket/uiflow_block_socket_udp_server_start.svg"> 

```python
udpsocket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
udpsocket.bind(('0.0.0.0', 5000))
```

<br><br>
- Send data to the specified IP and port
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/socket/uiflow_block_socket_udp_server_sendto.svg"> 

```python
udpsocket.sendto('Hello', ('192.168.31.11', 5000))
```

<br><br>
- Close the socket.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/socket/uiflow_block_socket_udp_server_close.svg"> 

```python
udpsocket.close()
```

<br><br>
- Block the receiving of listening data, set the maximum buffer length, and return when data is received.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/socket/uiflow_block_socket_udp_server_recv.svg"> 

```python
data = udpsocket.recv(1024)
```

<br><br>
- Block the receiving of listening data, and set the length of the receiving buffer, and return when the receiving buffer is full.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/socket/uiflow_block_socket_udp_server_read.svg"> 

```python
data = udpsocket.read(10)
```

