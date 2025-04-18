# NTP

## Example

Read the current time through the network server, Note: When the program download offline, you need to add WiFi connection program before NTP initialization program, so that the device connects to the network.


<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/ntp/uiflow_block_ntp_example.svg">


```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import ntptime
import time

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

ntp = ntptime.client(host='cn.pool.ntp.org', timezone=8)
while True:
  print(ntp.formatDatetime('-', ':'))
  print(ntp.getTimestamp())
  wait(1)
  wait_ms(2)
```


## API 

- Set the NTP server and time zone, and connect.
  - host:
    - `cn.pool.ntp.org`
    - `jp.pool.ntp.org`
    - `sg.pool.ntp.org`
    - `tw.pool.ntp.org`
    - `hk.pool.ntp.org`
    - `us.pool.ntp.org`
    - `de.pool.ntp.org`
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/ntp/uiflow_block_ntp_init_timezone.svg">

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/ntp/uiflow_block_ntp_init_timezone_dropdown.svg">

```python
import ntptime
ntp = ntptime.client(host='cn.pool.ntp.org', timezone=8)
```

<br><br>
- Retrieve the current date and set the delimiter.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/ntp/uiflow_block_ntp_get_date_format.svg">

```python
ntp.formatDate('-')
```

<br><br>
- Retrieve the current time and set the separator.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/ntp/uiflow_block_ntp_get_time_format.svg">

```python
ntp.formatTime(':')
```

<br><br>
- Read the current date and time, and set the date format separator and time format separator.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/ntp/uiflow_block_ntp_get_date_time_format.svg">

```python
ntp.formatDatetime('-', ':')
```


<br><br>
- Retrieve the current Unix timestamp
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/ntp/uiflow_block_ntp_get_timestamp.svg">

```python
ntp.getTimestamp()
```

<br><br>
- Read current year
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/ntp/uiflow_block_ntp_get_year.svg">

```python
ntp.year()
```

<br><br>
- Read current month
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/ntp/uiflow_block_ntp_get_month.svg">

```python
ntp.month()
```

<br><br>
- Retrieve the current day of the week
- return value:
  - Sunday:0 
  - Monday:1
  - Tuesday:2
  - Wednesday:3
  - Thursday:4
  - Friday:5
  - Saturday:6
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/ntp/uiflow_block_ntp_get_weekday.svg">

```python
ntp.weekday()
```


<br><br>
- Read current day
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/ntp/uiflow_block_ntp_get_day.svg">

```python
ntp.day()
```


<br><br>
- Read current hour
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/ntp/uiflow_block_ntp_get_hour.svg">

```python
ntp.hour()
```

<br><br>
- Read current minute
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/ntp/uiflow_block_ntp_get_minute.svg">

```python
ntp.minute()
```

<br><br>
- Read current second
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/advanced/ntp/uiflow_block_ntp_get_second.svg">

```python
ntp.second()
```



