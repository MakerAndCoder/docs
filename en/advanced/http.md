
# HTTP

## Example

### GET method


<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/http/uiflow_block_http_request_get_example.svg"> 


```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import urequests

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

try:
  req = urequests.request(method='GET', url='https://httpbin.org/get', headers={'Content-Type':'application/json'})
  print((str('Status: ') + str((req.status_code))))
  print(req.text)
  gc.collect()
  req.close()
except:
  print((str('Status: ') + str((req.status_code))))
  print('Fail')
```

### POST method

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/http/uiflow_block_http_request_post_example.svg"> 


```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import urequests
from libs.json_py import *

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

try:
  req = urequests.request(method='POST', url='https://httpbin.org/get',json={'Payload':(py_2_json({'msg':'hello'}))}, headers={'Accept':'application/json'})
  print((str('Status: ') + str((req.status_code))))
  print(req.text)
  gc.collect()
  req.close()
except:
  print((str('Status: ') + str((req.status_code))))
  print('Fail')
```


## API

- Create HTTP requests, methods support GET, POST, DELET, PUT, PATCH.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/http/uiflow_block_http_request.svg"> 

```python
try:
  req = urequests.request(method='GET', url='https://httpbin.org/get', headers={'Accept':'application/json'})
  print((str('Status: ') + str((req.status_code))))
  print(req.text)
  gc.collect()
  req.close()
except:
  print((str('Status: ') + str((req.status_code))))
  print('Fail')

```


<br><br>
- Return status code
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/http/uiflow_block_get_status_code.svg"> 

```python
print(req.status_code)
```


<br><br>
- Getting the returned request data
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/http/uiflow_block_get_data.svg"> 

```python
print(req.text)
```


