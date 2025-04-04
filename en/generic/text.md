# Text

## Example

How to use string functions

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_example.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import binascii

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

string = None
date = None

string = 'hello world'
print(string.upper())
print('hello')
print(string[0])
print(string.count('o'))
print(not len(string))
print(len(string))
print(string.replace('e', 'w'))
print('  MC4.0  '.strip())
print('hello olleh'.strip('h'))
print(str(2500))
print((str('Hi!') + str(string)))
date = binascii.hexlify('hello').decode()
print(date.encode())
print((binascii.unhexlify(date)).decode())
print("%.0f"%float(date))
```

## API
- Create text content
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_text.svg">

```python
string = 'helloworld'
```

<br><br>
- Concatenate text
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_text_add.svg">

```python
print(string.upper())
```

<br><br>
- Convert text content to uppercase or lowercase
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_text_changeCase.svg">

```python
print(string.upper())
```

<br><br>
- Extract a specified portion of text
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_text_charAt.svg">

```python
print(string[0])
```

<br><br>
- Return the number of occurrences of a specified character in the text
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_text_count.svg">

```python
print(string.count('o'))
```

<br><br>
- Check if the text is empty
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_text_isEmpty.svg">

```python
print(not len(string))
```

<br><br>
- Return the length of the text
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_text_length.svg">

```python
print(len(string))
```

<br><br>
- Convert other data types to strings
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_convent_str.svg">

```python
print(str(2500))
```

<br><br>
- Decode a string to a specified format
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_decode_str.svg">

```python
print((binascii.unhexlify(date)).decode())
```

<br><br>
- Convert a string back to a bytes object
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_encode_str.svg">

```python
print(date.encode())
```

<br><br>
- Encode a string to bytes
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_m5_text_bytestr_to_hexstr.svg">

```python
date = binascii.hexlify('hello').decode()
```

<br><br>
- Convert a string to a String
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_m5_text_hexstr_to_bytestr.svg">

```python
print((binascii.unhexlify(date)).decode())
```
<br><br>
- Perform string formatting to convert a float to a string without a decimal portion
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_text_math_split.svg">

```python
print("%.0f"%float(date))
```

<br><br>
- Print text
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_text_print.svg">

```python
print('')
```

<br><br>
- Replace text content
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_text_replace.svg">

```python
print(string.replace('e', 'w'))
```

<br><br>
- Remove leading and trailing whitespace from a string
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_text_trim.svg">

```python
print('  MC4.0  '.strip())
```

<br><br>
- Specify characters to remove from the beginning and end of a string
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_text_trim_string.svg">

```python
print('hello world'.strip('h'))
```

<br><br>
- Keep the string unescaped, containing all original characters
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_text_unescaped.svg">

```python
print('hello')
```

<br><br>
- Terminal prompt. Prompt for input with a message
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_text_prompt.svg">

<br><br>
- Terminal prompt. Customize the prompt for input with a message
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Text/uiflow_block_text_prompt_ext.svg">


