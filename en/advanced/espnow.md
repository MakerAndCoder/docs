# ESP-NOW

#>What is ESP-NOW? | ESP-NOW is a short-range, low-power communication protocol that allows multiple devices to communicate without or without using Wi-Fi. This protocol is similar to the low-power 2.4GHz wireless connection commonly seen in wireless mice - devices must be paired before communication. After pairing, the connection between devices is continuous, point-to-point, and does not require a handshake protocol.

## Example

### ESP-NOW Master

The master scans for the AP with the specified SSID to obtain the slave's MAC address, then adds it to the pairing list. In the main loop, it performs data transmission.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/espnow/uiflow_block_m5_espnow_master_example.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
from libs.mc_espnow import MCESPNOW
import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

flag_cb = None
slave_mac = None
slave_data = None
run = None
cnt_success = None
count_send = None
peer_mac = None
slave_ssid = None

now = MCESPNOW()

label8 = MCLabel('label0', x=66, y=49, color=0x000, font=FONT_MONT_14, parent=None)
label11 = MCLabel('label0', x=91, y=120, color=0x000, font=FONT_MONT_14, parent=None)
label1 = MCLabel('label0', x=149, y=36, color=0x000, font=FONT_MONT_14, parent=None)
label3 = MCLabel('label0', x=186, y=161, color=0x000, font=FONT_MONT_14, parent=None)
label5 = MCLabel('label0', x=170, y=96, color=0x000, font=FONT_MONT_14, parent=None)

peer_mac = None

def send_cb(flag):
  global flag_cb,slave_mac,slave_data,run,cnt_success,count_send,peer_mac,slave_ssid
  flag_cb = flag
  if flag_cb:
    cnt_success = cnt_success + 1
    label8.set_text(str(cnt_success))

  pass

def recv_cb(dummy):
  global flag_cb,slave_mac,slave_data,run,cnt_success,count_send,peer_mac,slave_ssid
  slave_mac, slave_data = now.espnow_recv_str()
  label11.set_text(str(slave_data))

  pass

def buttonA_wasPressed():
  global flag_cb, slave_mac, slave_data, run, cnt_success, count_send, peer_mac, slave_ssid
  run = 1
  pass
btnA.wasPressed(buttonA_wasPressed)

def buttonC_wasPressed():
  global flag_cb, slave_mac, slave_data, run, cnt_success, count_send, peer_mac, slave_ssid
  run = 0
  pass
btnC.wasPressed(buttonC_wasPressed)

now.espnow_init(1, 1)
count_send = 0
cnt_success = 0
flag_cb = 0
run = 0
slave_ssid = 'MC4.0_Slave'
while peer_mac == None:
  peer_mac = now.espnow_scan(1, slave_ssid)
label1.set_text(str(slave_ssid))
label3.set_text(str(peer_mac))
now.espnow_add_peer(peer_mac, 1, 0, False)
now.espnow_send_cb(send_cb)
now.espnow_recv_cb(recv_cb)
while True:
  if run:
    count_send = count_send + 1
    now.espnow_send_data(1, str(count_send))
    label5.set_text(str(count_send))
    wait_ms(1)
  wait_ms(2)
```

### ESP-NOW Slave

The slave opens an AP hotspot with a specified name (for the master to discover and obtain the MAC address), and in the reception callback, it obtains the sender's MAC address and data, and sends back the same data.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/espnow/uiflow_block_m5_espnow_slave_example.svg">


```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
from libs.mc_espnow import MCESPNOW

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

mac_addr = None
data = None
onetime = None
ssid = None

now = MCESPNOW()

label5 = MCLabel('label0', x=102, y=101, color=0x000, font=FONT_MONT_14, parent=None)
label8 = MCLabel('label1', x=162, y=66, color=0x000, font=FONT_MONT_14, parent=None)
label9 = MCLabel('label0', x=71, y=49, color=0x000, font=FONT_MONT_14, parent=None)
label1 = MCLabel('label0', x=154, y=31, color=0x000, font=FONT_MONT_14, parent=None)
label3 = MCLabel('label0', x=149, y=175, color=0x000, font=FONT_MONT_14, parent=None)

def recv_cb(dummy):
  global mac_addr,data,onetime,ssid
  mac_addr, data = now.espnow_recv_str()
  label5.set_text(str(mac_addr))
  label8.set_text(str(data))
  label9.set_text(str(data))
  if onetime:
    now.espnow_add_peer(mac_addr, 1, 0, False)
    now.espnow_recv_cb(recv_cb)
    onetime = 0
  now.espnow_send_data(1, data)

  pass

now.espnow_init(1, 1)
onetime = 1
ssid = 'MC4.0_Slave'
now.espnow_set_ap(ssid, '')
label1.set_text(str(ssid))
label3.set_text(str(now.espnow_get_mac(0)))
now.espnow_recv_cb(recv_cb)
```


## API
- Initialize ESP-NOW to a specific channel and configure the data type at the same time:
  - ch:0-13
  - type:
    - list: 0
    - string: 1
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/espnow/uiflow_block_m5_espnow_init_channel.svg">

```python
from libs.mc_espnow import MCESPNOW
now = MCESPNOW()
now.espnow_init(ch, type)
```


<br><br>
- Add a paired device and map it to a specific ID:
  - peer: Device MAC address
  - id:0-10
  - ifidx:s
    - ESP_IF_WIFI_STA:0
    - ESP_IF_WIFI_AP:1
  - encrypt:If encryption is enabled, fill in LMK
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/espnow/uiflow_block_m5_espnow_add_peer.svg">

```python
now.espnow_add_peer('', 1, 0, False)
```


<br><br>
- Send data to a device that has been added to the pairing list with a specified ID.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/espnow/uiflow_block_m5_espnow_send_data.svg">

```python
now.espnow_send_data(1, "Hello")
```

<br><br>
- Data send callback:
  - flag: Transmit Status Flag
    - Sent successfully:1
    - Send Failure:0
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/espnow/uiflow_block_m5_espnow_enable_send_cb.svg">

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/espnow/uiflow_block_m5_espnow_send_cb.svg">

```python
def send_cb(flag):
  global flag_cb
  flag_cb = flag
  pass

now.espnow_send_cb(send_cb)
```


<br><br>
- Broadcast data.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/espnow/uiflow_block_m5_espnow_broadcast_data.svg">

```python
now.espnow_broadcast_data('1234')
```

<br><br>
- Data reception callback
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/espnow/uiflow_block_m5_espnow_enable_recv_cb.svg">

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/espnow/uiflow_block_m5_espnow_recv_cb.svg">

```python
def recv_cb(dummy):
  slave_mac, slave_data = now.espnow_recv_str()
  print(str(slave_data))
  pass

now.espnow_recv_cb(recv_cb)
```

<br><br>
- Get local mac address
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/espnow/uiflow_block_m5_espnow_get_mac_address.svg">

```python
now.espnow_get_mac(0)
```

<br><br>
- Scans the specified AP SSID, and obtains its mac address. This feature is commonly used to discover and add new devices. 
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/espnow/uiflow_block_m5_espnow_get_remote_mac1.svg">

```python
peer_mac = now.espnow_scan(1, slave_ssid)
```

<br><br>
- Enable the AP hotspot, and specify the SSID and PASSWORD.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/espnow/uiflow_block_m5_espnow_set_ap_mode1.svg">

```python
now.espnow_set_ap(ssid, '')
```

<br><br>
- If encrypt is enabled when adding paired devices, both devices can realize encrypted communication by setting the same PMK (Primary Master Key) and encrypting the LMK with AES-128, if not, the default value will be used.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/espnow/uiflow_block_m5_espnow_set_pmk.svg">

```python
now.espnow_set_pmk('')
```


<br><br>
- ESP-NOW Deinit
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/espnow/uiflow_block_m5_espnow_deinit.svg">

```python
now.espnow_deinit()
```




