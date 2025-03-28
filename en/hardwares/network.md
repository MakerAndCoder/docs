# Network

## Example

### Example 1

Set the Wi-Fi name and password, connect to Wi-Fi, and print the connection result to the serial monitor.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_demo1.svg"> 

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import wifiCfg


screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

wifiCfg.doConnect('MC-R&D', '******')
print(wifiCfg.wlan_sta.isconnected())
```

### Example 2

Download the Esptouch app on your phone, upload the program to the MC4.0 device, and enter the Wi-Fi password in the Esptouch app. If the serial monitor shows a successful connection and displays the IP address, the device has successfully connected to Wi-Fi and will automatically connect to this Wi-Fi in the future.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_demo_smartconfig.svg"> 

1. After uploading the program to the MC4.0 device, enter the Wi-Fi password in the Esptouch app and click confirm.

<img alt="schematics" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_smartconfig_connect_wifi.png" width="20%" />

2. After completion, the device automatically connects to Wi-Fi and outputs the IP address.

<img alt="schematics" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_smartconfig_get_ip_address.png" width="50%" />

## API

- Attempts to automatically connect to a previously configured Wi-Fi network.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_wifi_connect.svg"> 

```python
wifiCfg.autoConnect(lcdShow=False)
```
<br /><br />

- Attempts to automatically connect to a previously configured Wi-Fi network and displays the connection status on the LCD.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_wifi_connect.svg"> 

```python
wifiCfg.autoConnect(lcdShow=True)
```
<br /><br />

- Attempts to reconnect to a previously configured and saved Wi-Fi network. This method is typically used to retry a connection after the device loses connection.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_reconnect.svg"> 

```python
wifiCfg.reconnect()
```
<br /><br />

- Sets the Wi-Fi name (SSID) and password.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_doConnect.svg"> 

```python
wifiCfg.doConnect('', '')
```
<br /><br />

- Represents sending a point-to-point message to a specified API Key.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_p2p.svg"> 

```python
sendP2PData('', '')
```
<br /><br />

- Retrieves received P2P (point-to-point) message data.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_getp2p.svg"> 

```python
str(getP2PData())
```
<br /><br />

- Creates a WLAN (Wireless Local Area Network) interface object. Choose the Wi-Fi mode:
  - Station mode: Connect to a local area Wi-Fi network.
  - Access point mode: Create your own Wi-Fi hotspot.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_wlan_create_station.svg"> 

```python
network.WLAN(network.STA_IF)
```
<br /><br />

- Configures the WLAN interface parameters.
  - `essid`: Sets the access point's SSID (network name).
  - `password`: Sets the access point's password.
  - `authmode`: Sets the access point's authentication mode.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_wlan_config_ap.svg"> 

```python
wlan.config(essid='', password='', authmode=network.AUTH_OPEN)
```
<br /><br />

- Activates the interface: This command is used to enable the device's Wi-Fi functionality, allowing it to begin wireless communication.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_wlan_active.svg"> 

```python
wlan.active(True)
```
<br /><br />
- Scans for nearby Wi-Fi networks and returns a list containing available network information.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_wlan_scan.svg"> 

```python
str(wlan.scan())
```
<br /><br />
- Checks if the ESP32 is connected to a Wi-Fi network.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_wlan_isconnected.svg"> 

```python
str(wlan.isconnected())
```
<br /><br />
- `ssid`: The name of the Wi-Fi network to connect to.
- `password`: The password for the Wi-Fi network.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_wlan_connect.svg"> 

```python
wlan.connect('your_SSID', 'your_PASSWORD')
```
<br /><br />

- Retrieves the device's MAC address and converts it to a string format.
- Retrieves the currently configured SSID (network name) and converts it to a string format.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_wlan_config.svg"> 

```python
str(wlan.config('mac'))
```

<br /><br />
- Retrieves the device's network configuration.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_wlan_ifconfig.svg"> 

```python
str(wlan.ifconfig())
```
<br /><br />
- Retrieves the current Wi-Fi connection status.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_wlan_status.svg"> 

```python
str(wlan.status())
```
<br /><br />
- Disconnects from the Wi-Fi network.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_wlan_disconnect.svg"> 

```python
wlan.disconnect()
```
<br /><br />
- `STAT_IDLE`: Wi-Fi idle status. The device is not currently attempting to connect to any Wi-Fi network.
- `STAT_CONNECTING`: Wi-Fi connecting status. The device is attempting to connect to the specified Wi-Fi network.
- `STAT_GOT_IP`: Wi-Fi connected and obtained an IP address. The device has successfully connected to the Wi-Fi network and received an IP address from the DHCP server.
- 
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_wlan_state_define.svg"> 

```python
str(1001)
```
<br /><br />
- `ESPTOUCH`: Uses the ESPTOUCH protocol for configuration. The Wi-Fi configuration information (SSID and password) is sent to the device via a mobile app, allowing it to connect to the specified Wi-Fi network.
- `AIRKISS`: Uses the AIRKISS protocol for configuration. AIRKISS is a wireless configuration protocol developed by Tencent, used to send Wi-Fi configuration information to the device.
-

 `ESPTOUCH_AIRKISS`: Uses both ESPTOUCH and AIRKISS protocols simultaneously for configuration. The device will listen to both protocols, and the mobile app can use either protocol to send Wi-Fi configuration information. The device will configure itself after receiving the information.


<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_smartconfig_set_type.svg"> 

```python
smartconfig.set_type(smartconfig.ESPTOUCH)
```
<br /><br />
- Starts the SmartConfig feature, putting the device into SmartConfig configuration mode, and waits to receive Wi-Fi configuration information (SSID and password) from the mobile app.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_smartconfig_start.svg"> 

```python
smartconfig.start()
```
<br /><br />
- Stops the SmartConfig feature and exits SmartConfig configuration mode.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_smartconfig_stop.svg"> 

```python
smartconfig.stop()
```
<br /><br />
- Retrieves the current status of SmartConfig.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_smartconfig_get_status.svg"> 

```python
str(smartconfig.status())
```
<br /><br />
- Retrieves the SSID (network name) received during the SmartConfig process.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_smartconfig_get_ssid.svg"> 

```python
str(smartconfig.get_ssid())
```
<br /><br />
- Retrieves the password received during the SmartConfig process.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_smartconfig_get_password.svg"> 

```python
str(smartconfig.get_password())
```
<br /><br />
- Retrieves the phone's IP address during the SmartConfig process.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_smartconfig_get_phoneip.svg"> 

```python
str(smartconfig.get_phoneip())
```
<br /><br />
- Represents the event when SmartConfig completes scanning for Wi-Fi networks.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/hardwares/network/uiflow_block_network_smartconfig_state_define.svg"> 

```python
str(smartconfig.get_phoneip())
```

