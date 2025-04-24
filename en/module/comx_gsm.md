# Module COMX GSM

## Example

#> Perform a Ping test, establish a TCP connection and send a message via a Maker and Coder device, while also sending and receiving HTTP requests, and display the results of these operations on the screen.

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/comx_gsm/uiflow_block_com_gsm_demo.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
from comx.sim800 import SIM800

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

gsm = SIM800()

label7 = MCLabel('label0', x=33, y=33, color=0x000, font=FONT_MONT_14, parent=None)
label1 = MCLabel('label0', x=114, y=59, color=0x000, font=FONT_MONT_14, parent=None)
label3 = MCLabel('label0', x=73, y=118, color=0x000, font=FONT_MONT_14, parent=None)
label5 = MCLabel('label0', x=158, y=137, color=0x000, font=FONT_MONT_14, parent=None)

label7.set_text(str(gsm.get_IMEI()))
label1.set_text(str((gsm.ping_request('www.makerandcoder.com'))[0]))
if gsm.tcp_client(0, '118.190.93.84', 2317, 'Hi MC4.0'):
  label5.set_text('Success')
else:
  label5.set_text('Unsuccess')
gsm.http_destroy()
label3.set_text(str(gsm.http_services(1, 'http://header.json-json.com/', 'application/x-www-form-urlencoded', 'Hi MC4.0')))
label3.set_text(str(gsm.http_services(1, 'http://api.makerandcoder.com/v1', 'application/json', 'Hi MC4.0')))
```

## API
- Checks the GPRS network registration status, returning whether the module has successfully registered to the GPRS network.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/comx_gsm/uiflow_block_com_gsm_check_gprs_network_registration.svg">

```python
gsm.get_gprs_network_registration()
```

<br><br>
- Checks the GPRS service status, confirming whether GPRS service is available.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/comx_gsm/uiflow_block_com_gsm_check_gprs_service.svg">

```python
gsm.check_gprs_service()
```

<br><br>
- Checks the network registration status, returning whether the module has successfully registered to a cellular network.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/comx_gsm/uiflow_block_com_gsm_check_network_registration.svg">

```python
gsm.get_network_registration()
```

<br><br>
- Checks the signal quality, returning the current signal strength information, which is used to assess the quality of the network connection.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/comx_gsm/uiflow_block_com_gsm_check_single_quality.svg">

```python
gsm.get_single_quality()
```

<br><br>
- Checks the module's status, returning the current operating status of the module, including whether it is functioning properly or if there are any errors.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/comx_gsm/uiflow_block_com_gsm_check_status.svg">

```python
gsm.check_status()
```

<br><br>
- Retrieves the SIM card's CCID (Integrated Circuit Card Identifier), which is the unique identifier of the SIM card.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/comx_gsm/uiflow_block_com_gsm_get_ccid.svg">

```python
gsm.get_CCID()
```

<br><br>
- Retrieves the device's IMEI (International Mobile Equipment Identity), which is the unique identifier used to identify mobile devices.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/comx_gsm/uiflow_block_com_gsm_get_imei.svg">

```python
gsm.get_IMEI()
```

<br><br>
- Destroys the HTTP session and frees resources. This is used to terminate the current HTTP connection.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/comx_gsm/uiflow_block_com_gsm_http_destroy.svg">

```python
gsm.http_destroy()
```

<br><br>
- Sends a request using the specified HTTP method (GET, POST, etc.) to a specific URL and processes the response.
  - **method**: Select the HTTP method, such as GET or POST.
  - **url**: Specify the target URL.
  - **content type**: Select the content type, such as JSON or TEXT. 
  - **payload**: The data payload to be sent in POST or PUT requests.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/comx_gsm/uiflow_block_com_gsm_http_service.svg">

```python
gsm.http_services(0, '', 'application/json', '')
```

<br><br>
- Sends a Ping request to the specified URL to test the responsiveness of that URL or the quality of the network connection.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/comx_gsm/uiflow_block_com_gsm_ping_request.svg">

```python
gsm.ping_request('')
```

<br><br>
- Sets the command echo mode. `0` disables echoing, `1` enables echoing. When set to OFF, the device will not echo back the command characters after sending AT commands.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/comx_gsm/uiflow_block_com_gsm_set_echo_mode.svg">

```python
gsm.set_command_echo_mode(0)
```

<br><br>
- Sets the context identifier (CID) for the PDP (Packet Data Protocol) address. CID is used to identify the network context.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/comx_gsm/uiflow_block_com_gsm_set_pdp_address.svg">

```python
gsm.PDP_address(1)
```

<br><br>
- Sets the PDP context status. Active means activating the PDP context for network connection and data transmission.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/comx_gsm/uiflow_block_com_gsm_set_pdp_context.svg">

```python
gsm.set_PDP_context_status(1)
```

<br><br>
- Creates a TCP client connection.
  - **method**: Specify as TCP protocol.
  - **IP**: The IP address of the target server.
  - **port**: The port number of the target server.
  - **payload**: The data payload to be sent.
  
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/comx_gsm/uiflow_block_com_gsm_tcp_client.svg">

```python
gsm.http_services(0, '', 'application/json', '')
```

